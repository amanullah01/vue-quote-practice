<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid
      :quotes="quotes"
      @quoteDeleted="deleteQuote"
    ></app-quote-grid>
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
import Header from "./components/Header.vue";
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
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete a quote first");
      }
      this.quotes.push(quote);
    },
    deleteQuote: function(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    "app-header": Header,
    "app-quote-grid": QuoteGrid,
    "app-new-quote": NewQuote
  }
};
</script>

<style></style>
