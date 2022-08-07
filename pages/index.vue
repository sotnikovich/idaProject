<template>
  <div class="main">
    <Header @create="createProduct" />
    <div class="content">
      <ProductForm @create="createProduct" />
      <ProductList :products="products" @remove="removeProduct" />
    </div>
  </div>
</template>

<script>
import ProductForm from "../components/ProductForm.vue";
import ProductList from "../components/ProductList.vue";
import Header from "../components/Header.vue";
import { products } from "../products";
export default {
  name: "IndexPage",
  data() {
    return {
      products
    };
  },
  components: { ProductForm, ProductList, Header },
  methods: {
    createProduct(product) {
      this.products.unshift(product);
    },
    removeProduct(product) {
      this.products = this.products.filter((p) => p.id !== product.id);
    },
  },
};
</script>
<style lang="scss">
body {
  background: rgba(255, 254, 251, 0.8);
  font-family: "Source Sans Pro";
  overflow-x: hidden;
  max-width: 1440px;
  min-width: 320px;
  margin: 0 auto;
  padding: 25px;

  @media (max-width: 695px) {
    padding: 15px;
  }

}

.main {
  width: 100%;
}

.content {
  display: flex;
}

h1 {
  font-style: normal;
  font-weight: 600;
  font-size: 28px;
  line-height: 35px;
  color: #3f3f3f;
  margin: 0;
}
</style>
