<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <appQuoteGrid :quotes="quotes" @deleteQuote="deleteQuote"></appQuoteGrid>
    <div class="col-sm-12 text-center">
      <div class="alert alert-info">Info: Click on a quote to delete it!</div>
    </div>
  </div>
</template>

<script>
import NewQuote from "./components/NewQuote";
import Header from "./components/Header";
import QuoteGrid from "./components/QuoteGrid";
export default {
  data: function() {
    return {
      quotes: ["Suffer Now, and live rest of your life as a champion!"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header

  },
  methods: {
    newQuote(quote) {
      if(this.quotes.length >= this.maxQuotes) {
        return alert("Please delete quotes first!");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style></style>
