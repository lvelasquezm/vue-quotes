<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <label for>Quote</label>
        <textarea class="form-control" placeholder="Enter your quote" rows="3" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew() {
      this.$emit("onNewQuote", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped>
.row {
  margin-top: 10px;
}

.btn {
  margin-bottom: 10px;
  margin-top: 10px;
}
</style>