<template>
  <div class="container">
    <Header />
    <main v-if="!loading">
      show data
    </main>
    <main v-else class="flex flex-col align-center justify-center text-center">
      <div class="text-gray-500 text-3xl mt-10 mb-6">Fetching data...</div>
      <img :src="loadingImage" class="w-24 m-auto">
    </main>
  </div>
</template>

<script>
// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/script-setup-2/active-rfcs/0000-script-setup.md

import Header from "./components/Header.vue";
import Hourglass from './assets/hourglass.gif'

export default {
  components: {
    Header,
  },
  data() {
    return {
      loading: true,
      title: 'Global',
      dataDate: '',
      stats: {},
      countries: [],
      loadingImage: Hourglass
    }
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch("https://api.covid19api.com/summary");
      const data = await res.json();
      return data;
    },
  },
  async created() {
    const data = await this.fetchCovidData();
    //console.log(data);
    this.dataDate = data.dataDate
    this.stats = data.Global
    this.countries = data.Countries
    this.loading = false

  },
};
</script>
