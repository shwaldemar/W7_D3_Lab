<template>
<p> {{this.countryList}}</p>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      countryList: []
    }
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
            .then(responce => responce.json())
            .then(countries => this.countryList = countries)
  },
  components: {

  }
}
</script>

<style>

</style>
