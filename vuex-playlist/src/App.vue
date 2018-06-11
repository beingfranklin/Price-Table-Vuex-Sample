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
    return {
      products: [
        { name: "Banana Skin", price: 20 },
        { name: "Shiny Star", price: 40 },
        { name: "Green Shells", price: 60 },
        { name: "Red Shells", price: 80 }
      ]
    };
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