<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a Quote to delete it.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
export default {
  name: "app",
  data: function() {
    return {
      quotes: ["This is a quote"],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote: function(quote) {
      this.quotes.push(quote);
    }
  },
  components: {
    "app-quote-grid": QuoteGrid,
    "app-new-quote": NewQuote
  }
};
</script>

<style></style>
