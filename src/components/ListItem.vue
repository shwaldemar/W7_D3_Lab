<template>
    <li v-on:click="handleClick"> {{country.name}}</li>
</template>

<script>
    import {eventBus} from '../main'

    export default {
        name: "list-item",
        props: ['country'],
        methods: {
            handleClick() {
                eventBus.$emit('country-selected', this.country)
            }
        }
    }
</script>

<style scoped>

</style>