<template lang="html">
  <div>
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
  methods: {
    handleClick() {
      eventBus.$emit('country-selected', this.country)
    }
  },
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
