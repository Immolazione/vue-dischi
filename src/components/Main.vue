<template>
<main class="background">
    <div class="vh-100">
        <div class="container">
            <section id="cards" class="d-flex flex-wrap row row-cols-6">
                <div class="single-card d-flex flex-column col mx-2" v-for="(card, index) in filteredSongs" :key="index">
                    <img class="px-4 pt-4" :src="card.poster" :alt="card.title">
                    <h1 id="title" class="text-white text-center p-2">{{card.title}}</h1>
                    <h5 id="author" class="text-center px-2 mb-0">{{card.author}}</h5>
                    <h6 id="year" class="text-center px-2">{{card.year}}</h6>
                </div>
            </section>
        </div>
    </div>
</main>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',
    data(){
        return {
            songsList: [],
        };
    },
    props: ['selectedGenre'],
    computed: {
        filteredSongs() {
            if (!this.selectedGenre) return this.songsList;
            return this.songsList.filter((song) => song.genre === this.selectedGenre);
        }
    },
    methods: {
        fetchSongs(){
            axios.get("https://flynn.boolean.careers/exercises/api/array/music").then(res => {

                this.songsList = res.data.response;

                const genres = [];
                this.songsList.forEach((song) => {
                    const { genre } = song;
                    if (!genres.includes(genre)) genres.push(genre);
                });

                this.$emit("genres-ready", genres);
            });
        },
    },
    created() {
        this.fetchSongs();
    }
};
</script>

<style scoped lang="scss">
@import '../assets/scss/style.scss';
.background {
    background-color: $main-color;
}
#cards{
    padding-top: 6rem;
    .single-card{
        // width: 10rem;
        height: 22rem;
        background-color: $header-color;
        margin-top: 2rem;
        img {
            width: 100%;
        }
        #title {
            font-size: 1.5rem;
        }
        #author, #year {
            color: $font-color;
        }
    }
}

</style>