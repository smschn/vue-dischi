<template>
    <header>
        <img src="../assets/spotify_logo.png" alt="Logo">
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
    position: relative;

    img {
        display: inline-block;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        margin-left: 30px;
    }
}
</style>