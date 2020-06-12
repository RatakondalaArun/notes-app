<template>
  <div class="row">
    <div class="col-12">
      <h1>Quotes Added</h1>
    </div>
    <div class="col-12">
      <div class="progress">
        <div
          class="progress-bar"
          role="progressbar"
          :style="{ width: calculateProgress() + '%' }"
          aria-valuenow="0"
          aria-valuemin="0"
          aria-valuemax="100"
        >
          {{ calculateProgress() / 10 }}/10
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    progress: {
      default: 0,
    },
  },
  data: function() {
    return {};
  },
  methods: {
    calculateProgress: function() {
      return parseInt((this.progress / 10) * 100);
    },
  },
};
</script>

<style scoped></style>
