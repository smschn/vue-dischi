<template>
    <div class="loader">
        Loading data...
    </div>
</template>

<script>
export default {
    name: 'MyLoader'
}
</script>

<style lang='scss'>
@import '../styles/variables.scss';

.loader {
    background-color: $grey;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    padding: 200px;
    font-size: 5rem;
}
</style>