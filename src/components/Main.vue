<template>
<main class="vh-100">
    <div class="vh-100 container">
        <section id="cards" class="d-flex justify-content-between">
            <div class="single-card" v-for="(card, index) in songsList.response" :key="index">
                <img :src="card.poster" :alt="CopertinaAlbum">
                <h1>{{card.title}}</h1>
                <h4>{{card.author}}</h4>
                <h4>{{card.year}}</h4>
            </div>
        </section>
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
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( response => {
            this.songsList = response.data;
            console.log(this.songsList);
        });
    }
};
</script>

<style scoped lang="scss">
@import '../assets/scss/_vars.scss';
main {
    background-color: $main-color;
}
#cards{
    .single-card{
        width: 8rem;
        height: 10rem;
        background-color: $header-color;
        margin-top: 2rem;
    }
}

</style>