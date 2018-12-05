<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <br>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <br>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import NewQuote from "./components/NewQuote.vue"
import QuoteGrid from "./components/QuoteGrid.vue"

export default {
  data: function() {
    return {
      quotes: [
        "Just a Quote to see something"
      ],
      maxQuotes: 10
    }
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appNewQuote: NewQuote,
    appQuoteGrid: QuoteGrid
  }
}
</script>

<style>
</style>
