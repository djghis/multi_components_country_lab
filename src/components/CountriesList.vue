<template lang="html">
  <div>
    <label for="country_select">Select a country</label>
    <select class="list">
      <option disabled value="">Select a country</option>
      <option v-for="(country, index) in countries" :country="country" :key="index">{{country.name}}</option>
    </select>
    <!-- <ul>
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul> -->

  </div>
</template>

<script>
import ListItem from './ListItem.vue';

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
