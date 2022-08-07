<template>
  <transition-group name="post-list">
    <ProductItem v-for="product in products" :product="product" :key="product.id" @remove="$emit('remove', product)" />
  </transition-group>
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
<style lang="scss" scoped>
span {
  display: grid;
  grid-template-columns: repeat(auto-fit, 335px);
  gap: 15px;
  width: 100%;
  margin-left: 16px;

  @media (max-width: 1044px) {
    margin: 0;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  }

  @media (max-width: 695px) {
    margin: 0;
    grid-template-columns: repeat(auto-fit, minmax(335px, 1fr));
  }

}

.post-list-enter-active,
.post-list-leave-active {
  transition: all 0.4s ease;
}

.post-list-enter-from,
.post-list-leave-to {
  opacity: 0;
  transform: translateX(130px);
}

.post-list-move {
  transition: transform 0.4s ease;
}
</style>
