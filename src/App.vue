<template>
  <div id="app">
    <div class="container">
      <h1>Todo List</h1>
      <!-- <QuoteProgress :progress="totalQuotes"></QuoteProgress> -->
      <CreateNote @onAddItem="addQuote($event)"></CreateNote>
      <TodoGrid :list="list" @onRemoveCard="discardCard($event)"></TodoGrid>
      <div class="row" v-if="list.length>=10">
        <div class="col-12">
          <div class="alert alert-danger" role="alert">You can only add 10 Quote😁</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import QuoteProgress from "./components/QuoteProgress";
import CreateNote from "./components/CreateNote";
import TodoGrid from "./components/TodoGrid";
export default {
  name: "App",
  components: {
    CreateNote,
    TodoGrid
    // QuoteProgress
  },

  data: function() {
    return {
      list: []
    };
  },
  computed: {
    totalQuotes: function() {
      return this.list.length;
    }
  },
  methods: {
    addQuote: function(data) {
      if (this.list.length < 10) {
        this.list.unshift(data);
      }
    },
    discardCard: function(index) {
      this.list.splice(index, 1);
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
