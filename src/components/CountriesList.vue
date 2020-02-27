<template lang="html">
  <div>
    <label for="country_select">Select a country</label>
    <select v-model="selectedCountry" @change="handleChange" >
      <option disabled value="">Select a country</option>
      <option v-for="(country, index) in countries" :country="country" :key="index" :value="index">{{country.name}}</option>
    </select>
    <!-- <ul>
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul> -->

  </div>
</template>

<script>
import ListItem from './ListItem.vue';
import {eventBus} from '../main.js'

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    // "list-item": ListItem
  },
  data() {
    return{
      selectedCountry: null
    }
  },
  methods: {
    handleChange(event){
      eventBus.$emit('country-selected', this.countries[event.target.value])
    }
  }
}
</script>

<style lang="css" scoped>
</style>
