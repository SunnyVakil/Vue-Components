<template >
  <div class="conatiner">
    <app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <br />
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <br />
    <app-quote-grid v-bind:quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to Delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: ["Just Type to See Something"],
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
      if (this.quotes.length >= this.maxQuotes) {
        alert("Please Delete a Quote First!");
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
body {
  padding: 1.125em;
}

.row {
  margin-top: 1em;
}

app-quote-grid {
  margin: 1.125em;
}
</style>

