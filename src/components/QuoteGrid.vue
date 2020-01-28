<template>
  <div class="row">
    <app-quote v-for="(quote, i) in quotes" :key="i">{{ quote }}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
  props: ["quotes"],
  components: {
    "app-quote": Quote
  }
};
</script>

<style scoped></style>
