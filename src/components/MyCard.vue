<template>
    <div class="card">
        <div class="album_cover">
            <img v-bind:src="info.poster" v-bind:alt="info.title">
        </div>
        <div class="album_title">
            {{info.title}}
        </div>
        <div class="album_author">
            {{info.author}}
        </div>
        <div class="album_year">
            {{info.year}}
        </div>
    </div>    
</template>

<script>
export default {
    name: 'MyCard',
    props: {
        info: Object
    }
}
</script>

<style lang='scss'>
@import '../styles/variables.scss';
@import '../styles/general.scss';

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
</style>