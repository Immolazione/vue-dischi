<template>
<main class="vh-100">
    <div class="vh-100 container">
        <section id="cards" class="d-flex justify-content-between">
            <div class="single-card">
                <img src="" alt="">
            </div>
        </section>
    </div>
</main>
</template>

<script>
export default {
name: 'Main',
    data(){
        return {
            songsList: [],
        };
    },
    methods: {
        getSongCard(){
            // axios.get('https://flynn.boolean.careers/exercises/api/array/music').then(res => {

            // });
        },

    }
}
</script>

<style scoped lang="scss">
@import '../assets/scss/_vars.scss';
main {
    background-color: $main-color;
}

</style>