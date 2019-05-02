<template lang="html">
  <div>
    <!-- <ul> -->
    <select v-on:change="showDetail"
    v-model="selectedCountry">

      <option v-for="(country, index) in countries"
      v-bind:country="country" v-bind:key="index" v-bind:value="country"
      >{{country.name}}</option>

    </select>
    <!-- </ul> -->
  </div>
</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: 'countries-list',
  props: ['countries'],
  data() {
    return {
      selectedCountry: ''
    };
  },
  // components: {
  //   "list-component": ListComponent
  // },
  methods: {
    showDetail: function() {
      eventBus.$emit('country-selected', this.selectedCountry)
      console.log('bus', this.selectedCountry);
    }
}
}
</script>

<style lang="css" scoped>
</style>
