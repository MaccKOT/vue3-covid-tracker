<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ text }}</h2>
    <div class="text-2x mt-4 mb-10">{{ timestamp }}</div>
  </div>
</template>

<script>
import dayjs from "dayjs";

export default {
  name: "DataTitle",
  props: ["text", "dataDate"],
  computed: {
    timestamp: function () {
      return dayjs(this.dataDate).format("MMMM D YYYY, hh:mm");
    },
  },
};
</script>
