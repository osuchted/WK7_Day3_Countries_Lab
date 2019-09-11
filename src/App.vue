<template lang="html">
  <div>
    <h1>Countries</h1>
    <div class="main-container">
      <countries-list :countries='countries'></countries-list>
      <country-detail :country='selectedCountry'></country-detail>
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import { eventBus } from './main.js'

export default {
  name: 'app',
  props: ['country'],
  data() {
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country
    })
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail
  }
}
</script>

<style lang="css" scoped>
  .main-container {
    display: flex;
    justify-content: space-between;
    font-family: sans-serif;;
  }

  article {
    border: 2px dashed navy;
    width: 300px;
    height: 400px;
    padding: 10px;
    margin-right:50px;
    font-weight: normal;
    border-radius: 10px;
  }


</style>
