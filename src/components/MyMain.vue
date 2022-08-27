<template>
    <main>
        <div class="container">
            <div class="card" v-for="(album, index) in albums" v-bind:key="index">
                <div class="album_cover">
                    <img v-bind:src="album.poster" v-bind:alt="album.title">
                </div>
                <div class="album_title">
                    {{album.title}}
                </div>
                <div class="album_author">
                    {{album.author}}
                </div>
                <div class="album_year">
                    {{album.year}}
                </div>
            </div>  
        </div>
    </main>
</template>

<script>
import axios from 'axios' ;

export default {
    name: 'MyMain',
    data() {
        return {
            albums: ''
        }
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => {
            this.albums = response.data.response;
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

    .card {
        background-color: $bgCard;
        flex-basis: calc(100% / 6);
        margin: 20px;
        color: #fff;
        padding: 20px;

        .album_cover,
        .album_title,
        .album_author,
        .album_year {
            margin: auto;
            padding: 5px;

            img {
                width: 150px;
            }
        }
        
        .album_author,
        .album_year {
            color: $grey;
        }

        .album_title {
            text-transform: uppercase;
            font-weight: 600;
        }
    }
}
</style>