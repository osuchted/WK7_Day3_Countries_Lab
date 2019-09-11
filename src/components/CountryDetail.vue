<template lang="html">
  <article v-if="country">
    <h1>{{ country.name }}</h1>
    <p>{{ country.capital }}</p>
    <p>{{ country.region }}</p>
    <p>{{ country.population }}</p>
    <p>{{ country.region }}</p>
    <em>Language</em>
    <p>{{ country.languages[0].name }}</p>
    <p><img :src="country.flag" style="width:50%; height:50%"/></p>
  </article>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
em {
  color:red;
}
</style>
