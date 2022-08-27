<template>
    <main>
        <div class="container">
            <div class="card">
                <div class="album_cover">
                    img
                </div>
                <div class="album_title">
                    wembley
                </div>
                <div class="artist_name">
                    queen
                </div>
            </div>
               
        </div>
    </main>
</template>

<script>
import axios from 'axios' ;

export default {
    name: 'MyMain',
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(response => {
            console.log(response.data.response);
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

    .card {
        background-color: $bgCard;
        flex-basis: calc(100% / 5);
        margin: 20px;
        color: #fff;

        .album_cover,
        .album_title,
        .artist_name {
            width: 80%;
            margin: auto;
            padding: 5px;
        }
    }
}
</style>