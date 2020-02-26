<template lang="html">
  <p v-on:click="handleClick">{{country.name}}</p>
</template>

<script>
import {eventBus} from '../main.js'
export default {
    name: 'country-list-item',
    props: ['country'],
    methods: {
      handleClick(){
        eventBus.$emit('country-selected', this.country)
      }
    }
}
</script>

<style lang="css" scoped>
</style>
