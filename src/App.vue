<template>
<!--<p> {{this.countryList}}</p>-->
  <country-list :countryList="countryList"></country-list>
</template>

<script>
import CountryList from './components/CountryList';

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
    'country-list': CountryList
  }
}
</script>

<style>

</style>
