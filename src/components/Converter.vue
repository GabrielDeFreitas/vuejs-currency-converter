<template>
  <div class="converter">
    <h2>{{ baseCurrency }} to {{ targetCurrency }}</h2>
    <input type="text" v-model="baseAmount" v-bind:placeholder="baseCurrency">
    <input type="button" value="Converter" @click="convert">
    <h3>{{ targetAmount }}</h3>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'CurrencyConverter',
  props: ["baseCurrency", "targetCurrency"],
  data() {
    return {
      baseAmount: "",
      targetAmount: 0,
      apiKey: process.env.VUE_APP_API_KEY,
      apiUrl: 'https://openexchangerates.org/api/'
    }
  },
  methods: {
    async convert() {
      try {
        const response = await axios.get(`${this.apiUrl}latest.json?app_id=${this.apiKey}`);
        const rates = response.data.rates;

        const baseAmount = parseFloat(this.baseAmount);
        const targetRate = parseFloat(rates[this.targetCurrency]);

        console.log('Base Amount:', baseAmount);
        console.log('Target Currency Rate:', targetRate);

        if (!isNaN(baseAmount) && !isNaN(targetRate)) {
          this.targetAmount = (baseAmount * targetRate).toFixed(2);
          console.log('Converted Amount:', this.targetAmount);
        } else {
          console.error('Enter a valid numeric value for conversion.');
        }
      } catch (error) {
        console.error('Error converting currency:', error);
      }
    }
  }
};
</script>

<style scoped>

:root {
  --primary-200: #fcd085;
  --primary-400: #ffbc48;
}

.converter {
  background-color: #444448;
  padding: 2.8rem;
  border-radius: 0.8rem;
  color: white;
}

</style>

