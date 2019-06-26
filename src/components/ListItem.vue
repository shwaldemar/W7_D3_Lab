<template>
    <li> {{this.country.name}}</li>
</template>

<script>
    export default {
        name: "list-item",
        props: ['country']
    }
</script>

<style scoped>

</style>