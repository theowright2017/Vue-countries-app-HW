<template lang="html">
  <div >
    <p>country detail</p>
    <h3>name: {{country.name}}</h3>
    <p>capital: {{country.capital}}</p>
    <p>population: {{country.population}}</p>
  </div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
