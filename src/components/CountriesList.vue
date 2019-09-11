<template lang="html">
  <div>
    <!-- <label for="country">Select Country</label>
    <select id="country" v-model="selectedCountry">
      <option value="" disabled selected>Select a Country</option>
      <option v-for="(country, index) in countries" :country="country" :key="index" v-on:change="handleClick">{{country.name}}</option>
    </select> -->
    <ul>
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul>
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
