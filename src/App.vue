<template lang="html">
<div>
  <h1>Countries</h1>
  <div class="main">
    <countries-list v-bind:countries='countries'></countries-list>
    <country-detail v-bind:country='selectedCountry'></country-detail>
  </div>
</div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import CountryDetail from './components/CountryDetail.vue'
import ListComponent from './components/ListComponent.vue'
import {eventBus} from './main.js'


export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(countries => this.countries = countries);
    // console.log(this.countries);

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    });
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail
  }
}
</script>

<style lang="css" scoped>
</style>
