<template>
  <div class="row">
    <appQuote
      v-for="(quote, index) in quotes"
      :key="index + quote"
      @click.native="deleteQuote(index)"
    >{{ quote }}</appQuote>
  </div>
</template>

<script>
import Quote from "./Quote";
export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit('deleteQuote', index);
    }
  }
};
</script>

<style >
</style>