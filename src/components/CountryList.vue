<template>
    <div>
        <ul>
            <list-item  v-for="(country, index) in countryList" :country="country"></list-item>
        </ul>
    </div>
</template>

<script>
    import ListItem from './ListItem'

    export default {
        name: "country-list",
        components: {ListItem},
        comments: {
            'list-item': ListItem
        },
        props: ['countryList']
    }
</script>

<style scoped>

</style>