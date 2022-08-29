<template>
    <header>
        <div class="container_h">
            <img src="../assets/spotify_logo.png" alt="Logo">
            <select name="ciao" id="ciao2">
                <option value="">Seleziona genere</option>
                <option value="prova1">ciao</option>
                <option value="prova2">sono</option>
                <option value="prova3">un</option>
                <option value="prova4">genere</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: 'MyHeader'
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
    }
}
</style>