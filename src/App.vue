<template>
<!--<p> {{this.countryList}}</p>-->
  <div class="main-container">
  <country-list :countryList="countryList"></country-list>
  <country-details :country="selectedCountry"></country-details>
  </div>
</template>

<script>
import CountryList from './components/CountryList';
import CountryDetails from './components/CountryDetails'
import {eventBus} from "./main";

export default {
  name: 'app',
  data() {
    return {
      countryList: [],
      selectedCountry: null
    }
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
            .then(responce => responce.json())
            .then(countries => this.countryList = countries);

    eventBus.$on('country-selected', (country) => {this.selectedCountry = country})
  },
  components: {
    'country-list': CountryList,
    'country-details': CountryDetails
  }
}
</script>

<style>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>
