<template>
  <div class="row">
    <app-quote
      v-for="(quote, index) in quotes"
      :key="quote"
      :quote="quote"
      @click.native="deleteQuote(index)"
    ></app-quote>
  </div>
</template>

<script>
import Quote from "./Quote";

export default {
  props: {
    quotes: Array
  },
  components: {
    "app-quote": Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("onDeleteQuote", index);
    }
  }
};
</script>

<style>
</style>