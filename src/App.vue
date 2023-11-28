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
body {
  background-color: #121214;
  position: absolute;
  inset: 0;
  height: 100%;
  width: 100%;
  background-image: linear-gradient(to right, #80808012 1px, transparent 1px),
  linear-gradient(to bottom, #80808012 1px, transparent 1px);
  background-size: 24px 24px;
  padding-inline: 2.2rem;
    max-width: 40rem;
    margin: 3.2rem auto;
}
</style>
