<template lang="html">
  <div v-if="country" class="styleMePls">
    <h3>{{country.name}}</h3>
    <p>Population: {{country.population}}</p>
    <p>Capital: {{country.capital}}</p>
    <p>Capital: {{country.capital}}</p>
    <p >{{country.languages.name}}</p>
    <img :src="country.flag"></img>

  </div>
</template>

<script>
export default{
  name: 'country-detail',
  props: ['country']

}
</script>

<style lang="css" scoped>
.styleMePls {
  position: absolute;
  top: 0px;
  right: 400px;
  max-width: 300px;
  max-height: 300px;
}
.styleMePls img {
  max-width: 100px;
  max-height: 100px;
}
</style>
