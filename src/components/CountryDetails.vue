<template>
    <div v-if="country">
    <h3> {{country.name}} </h3>
    <p> Capital: {{country.capital}} </p>
    <p> Population: {{country.population}} </p>
    </div>
</template>

<script>
    export default {
        name: "Country-details",
        props: ['country']
    }
</script>

<style scoped>

</style>