<template>
    <div id="product-one">
        <h2>Product List One</h2>
        <ul>
            <li v-for="product in products">
                <span class="name">{{ product.name }}</span>
                <span class="price">${{ product.price }}</span>
            </li>
        </ul>
        <h2>Product List On Sale</h2>
         <ul>
            <li v-for="product in saleProducts">
                <span class="name">{{ product.name }}</span>
                <span class="price">${{ product.price }}</span>
            </li>
        </ul>
        <button v-on:click="reducePrice">Reduce Price</button>
    </div>
</template>

<script>
export default {
  computed: {
    products() {
      return this.$store.state.products;
    },
    //Name needed to access the getter
    saleProducts() {
      return this.$store.getters.saleProducts;
    }
  },
  methods: {
    reducePrice: function() {
      // this.$store.state.products.forEach(product => {
      //   product.price -= 1;
      // });
      // this.$store.commit("reducePrice");
      //Fires up the reducedPrice mutation

      this.$store.dispatch("reducePrice");
    }
  }
};
</script>

<style scoped>
#product-one {
  background: #fff8b1;
  box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  margin-bottom: 30px;
  padding: 10px 20px;
}
#product-one ul {
  padding: 0;
}
#product-one li {
  display: inline-block;
  margin-right: 10px;
  margin-top: 10px;
  padding: 20px;
  background: rgba(255, 255, 255, 0.7);
}
.price {
  font-weight: bold;
  color: #e8800c;
}
</style>
