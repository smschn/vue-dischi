<template>
    <main>
         <div class="container">
            <MyCard v-for="(album, index) in albums" v-bind:key="index" :info="album" />
         </div>
        <MyLoader v-if="isLoading"/>
    </main>
</template>

<script>
import axios from 'axios' ;
import MyLoader from './MyLoader.vue';
import MyCard from './MyCard.vue';

export default {
    name: 'MyMain',
    components: {
        MyLoader,
        MyCard
    },
    data() {
        return {
            albums: [],
            isLoading: true,
            genres: []
        }
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => {
            this.albums = response.data.response; // response è un array di oggetti
            this.albums.forEach( album => {
                if (!this.genres.includes(album.genre)) {
                    this.genres.push(album.genre);
                }
            });
            this.isLoading = false;
            this.$emit('genresReady', this.genres); // preparo ad inviare array generi al padre 'app.vue'
        })
    }
}
</script>

<style lang='scss'>
@import '../styles/variables.scss';
@import '../styles/general.scss';

main {
    background-color: $bgMain;
    height: calc(100vh - 80px);
    text-align: center;
}
</style>