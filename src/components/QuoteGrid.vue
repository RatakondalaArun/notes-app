<template>
  <div class="row">
    <div v-for="(quote, index) in quotes" :key="index" class="col-4">
      <div class="card quote-area" @click="removeCard(index)">
        <div class="card-body" style="text-align:left;white-space:pre">{{ quote }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quotes"],
  data: function() {
    return {};
  },
  methods: {
    removeCard: function(index) {
      this.$emit("onRemoveCard", index);
    }
  }
};
</script>

<style scoped>
.quote-area {
  margin: 10px 10px 10px 10px;
  transition: 250ms;
}

.quote-area:hover {
  box-shadow: 0px 1px 5px 1px rgba(128, 128, 128, 0.496);
  background-color: rgba(94, 238, 245, 0.19);
}
</style>
