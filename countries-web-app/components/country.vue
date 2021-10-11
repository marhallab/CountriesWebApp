<template>
  <div>
    <b-card
      :title="countryName"
      :img-src="countryFlag"
      img-height="175"
      img-width="300"
      style="width: 350px"
      class="mb-2"
    >
      <b-card-text> <b>Population:</b> {{ countryPopulation }} </b-card-text>

      <b-card-text> <b>Region:</b> {{ countryRegion }} </b-card-text>

      <b-card-text>
       
        <div v-for="capital in countryCapital" :key="capital">
         <b>Capital:</b>  {{ capital }}
        </div></b-card-text
      >
    </b-card>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    countryName: String,
    countryFlag: String,
    countryPopulation: Number,
    countryRegion: String,
    countryCapital: Array,
  },
});
</script>