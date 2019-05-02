<!-- <template lang="html">


    <option v-on:click="showDetail">{{country.name}}</option>

</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['country'],
  methods: {
    showDetail: function() {
      eventBus.$emit('country-selected', this.country)
      // console.log('bus', this.country);
    }
  }
}
</script>

<style lang="css" scoped>
</style> -->
