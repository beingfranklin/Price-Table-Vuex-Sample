<template>
  <div id="app">
      <product-one v-bind:products="products"></product-one>
      <product-two v-bind:products="products"></product-two>
  </div>
</template>

<script>
console.log("App.vue begin");
import ProductOne from "./components/ProductOne.vue";
import ProductTwo from "./components/ProductTwo.vue";
export default {
  name: "app",
  components: {
    "product-one": ProductOne,
    "product-two": ProductTwo
  },

  data() {
    return {};
  }
};
console.log("App.vue end");
</script>

<style>
body {
  font-family: Ubuntu;
  color: #555;
}
</style>