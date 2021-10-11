<template>
  <div class="index w-100 d-flex flex-row justify-content-around flex-wrap">
    <div v-for="country in countries" :key="country.name">
      <Country
        :countryName="country.name.common"
        :countryFlag="country.flags.svg"
        :countryPopulation="country.population"
        :countryRegion="country.region"
        :countryCapital="country.capital"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  async asyncData({ $axios }) {
    const apiURL = "https://restcountries.com/v3.1/all";
    const countries = await $axios.$get(apiURL);
    return { countries };
  },
});
</script>
