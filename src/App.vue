<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @onNewQuote="addQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @onDeleteQuote="deleteQuote"></app-quote-grid>
    <div class="row" v-if="quotes.length">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">You can click on a quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header";
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";

export default {
  components: {
    "app-header": Header,
    "app-quote-grid": QuoteGrid,
    "app-new-quote": NewQuote
  },
  data() {
    return {
      quotes: [],
      maxQuotes: 10
    };
  },
  methods: {
    addQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert(
          "You have reached the maximum amount of quotes, please remove one first."
        );
      }

      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
