<template>
    <header>
        <div class="container_h">
            <img src="../assets/spotify_logo.png" alt="Logo">
            <select v-model="genreFilter" @change="chosenGenre">
                <option value="">Seleziona un genere</option>
                <option v-for="(genre, index) in genresList" v-bind:key="index" v-bind:value="genre">{{genre}}</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: 'MyHeader',
    props: {
        genresList: Array
    },
    data() {
        return {
            genreFilter: ''
        }
    },
    methods: {
        chosenGenre() {
            // console.log(`${this.genreFilter} - header.vue: genere scelto`);
            this.$emit('changedGenre', this.genreFilter); // invio il genere scelto al padre app.vue
        }
    }
}
</script>

<style lang='scss'>
@import '../styles/variables.scss';

header {
    height: 80px;
    background-color: $bgHeader;

    .container_h {
        height: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0px 30px;

        select {
            padding: 10px;
        }
    }
}
</style>