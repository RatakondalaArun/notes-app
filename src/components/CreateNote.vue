<template>
  <div id="area">
    <div class="row justify-content-center">
      <div class="col-5">
        <label for="text-field" class="align-left">Create Note</label>
        <textarea
          class="form-control"
          id="text-field"
          v-model="data"
          rows="3"
          placeholder="Add notes..."
        ></textarea>
        <button class="btn btn-primary" @click="addItem">Add</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      data: ""
    };
  },
  methods: {
    addItem: function() {
      if (this.data != "") {
        this.$emit("onAddItem", this.data);
        this.data = "";
      }
    }
  }
};
</script>

<style scoped>
#area {
  margin: 10px 10px 10px 10px;
}

#text-field {
  margin: 10px 10px 10px 10px;
}

.align-left {
  float: left;
}
</style>
