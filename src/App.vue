<template>
  <div class="container">
    <app-quote-grid :quotes="quotes"></app-quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
export default {
  name: "app",
  data: function() {
    return {
      quotes: ["This is a quote"],
      maxQuotes: 10
    };
  },
  components: {
    "app-quote-grid": QuoteGrid
  }
};
</script>

<style></style>
