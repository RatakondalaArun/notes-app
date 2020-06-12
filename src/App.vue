<template>
  <div id="app">
    <div class="container">
      <QuoteProgress :progress="totalQuotes"></QuoteProgress>
      <QuoteInputField @onAddQuote="addQuote($event)"></QuoteInputField>
      <QuoteGrid :quotes="quotes" @onRemoveCard="discardCard($event)"></QuoteGrid>
      <div class="row" v-if="quotes.length>=10">
        <div class="col-12">
          <div class="alert alert-danger" role="alert">You can only add 10 Quote😁</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteProgress from "./components/QuoteProgress";
import QuoteInputField from "./components/QuoteInputField";
import QuoteGrid from "./components/QuoteGrid";
export default {
  name: "App",
  components: {
    QuoteInputField,
    QuoteGrid,
    QuoteProgress
  },

  data: function() {
    return {
      quotes: []
    };
  },
  computed: {
    totalQuotes: function() {
      return this.quotes.length;
    }
  },
  methods: {
    addQuote: function(data) {
      if (this.quotes.length < 10) {
        this.quotes.unshift(data);
      }
    },
    discardCard: function(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
