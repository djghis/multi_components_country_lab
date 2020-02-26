<template>
  <div id="app">
    <h1>Countries</h1>
    <div class="main-container">
      <countries-list :countries='countries'></countries-list>
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';



export default {
  name: 'App',
  data(){
    return {
      countries: []
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)
  },
  components: {
    "countries-list": CountriesList
  }
}
</script>

<style>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
