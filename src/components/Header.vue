<template>
  <header class="text-center bg-blue-800 text-white p-4 mb-10">
    <div
      class="text-3xl md:text-5xl font-bold mb-3 flex flex-row justify-center items-center text-center gap-5"
    >
      <img :src="logopath" width="110" />
      Covid-19 Tracker
    </div>
    <p>
      API by
      <a href="https://covid19api.com/" targer="_blank">covid19api.com</a>
    </p>
  </header>
</template>

<script>
import Logo from "../assets/covid-19.png";

export default {
  name: "Header",
  data() {
    return {
      logopath: Logo,
    };
  },
};
</script>
