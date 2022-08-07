<template>
  <div class="productList">
    <ProductItem v-for="product in products" :product="product" />
  </div>
</template>
<script>
import ProductItem from "./ProductItem.vue";
export default {
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  components: { ProductItem },
};
</script>
<style lang="scss">
.productList {
  display: grid;
  grid-template-columns: repeat(auto-fit, 335px);
  gap: 15px;
  width: 100%;
  margin-left: 16px;

  @media (max-width: 695px) {
    margin: 0;
    grid-template-columns: repeat(auto-fit, minmax(335px, 1fr));
  }
}
</style>
