<template>
  <h1 v-for="(country,index) in countries" :key="index">
      {{ country.Country }}
  </h1>
</template>

<script>
export default {
    name:"CountrySelect",
    props:['countries']

}
</script>

<style>

</style>