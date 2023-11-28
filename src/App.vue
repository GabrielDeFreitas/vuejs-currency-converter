<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <CurrencyConverter baseCurrency="USD" targetCurrency="BRL"/>
</template>

<script>
import CurrencyConverter from './components/Converter.vue';

export default {
  name: 'App',
  components: {
    CurrencyConverter
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
