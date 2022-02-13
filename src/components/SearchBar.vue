<template> 
<section class="text-white fs-4">
    <label for="genre">Choose a Genre:</label>

    <select class="ms-1" name="genre" id="genre">
        <option value="">--</option>

    </select>
</section>
</template>

<script>
import axios from 'axios';
export default {
    name: 'SearchBar',
    data(){
        return {   
        genreList: [],
        };
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( res => {
            // console.log(res.data.response);

            for (let i = 0; i < res.data.response; i++) {
            let [index] = this.res.data.response;
            this.genreList += index.genre;
            }

            console.table(`genreList ${this.genreList}`);
        });
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/scss/style.scss';
select {
    border: 2px solid #fff;
    background-color: $main-color;
}
</style>