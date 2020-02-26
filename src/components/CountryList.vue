<template lang="html">
  <div >
    <h1 class="pop">Countries</h1>
    <ul>
        <select @change="handleChange">
          <option v-for="(country, index) in countries" :value="index" :country="country" :key="index">
            {{country.name}}
          </option>
        </select>
    </ul>
  </div>

</template>
<!-- <country-list-item v-for="(country, index) in countries" :country="country" :key="index"></country-list-item> -->
<script>
import {eventBus} from '../main.js'
import ListItem from './ListItem.vue'
export default {
  name: 'country-list',
  props: ['countries'],
  components: {
    'country-list-item': ListItem
  },
  methods: {
    handleChange(event){
      // get the eventbus
      // emit on the same frequency as the ListItem
      // send the payload: this.countries[event.target.value]
      eventBus.$emit('country-selected', this.countries[event.target.value])
      console.log(event.target.value);
    }
  }
}
</script>

<style lang="css" scoped>
.pop{
  margin-top: 0px;
}
</style>
