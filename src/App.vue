<template>
  <div id="app">
    <country-list :countries='countries'></country-list>
    <country-detail :country="selectedCountry"/>
  </div>
</template>

<script>
import CountryDetail from './components/CountryDetail.vue'
import CountryList from './components/CountryList.vue'

import {eventBus} from './main.js'
export default {
  name: 'App',
  data() {
    return {
      countries: [],
      selectedCountry: null
    };
  },
  components: {
    "country-list": CountryList,
    "country-detail": CountryDetail
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all/')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      // console.log(country);
      this.selectedCountry = country;
    })
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;

}
</style>
