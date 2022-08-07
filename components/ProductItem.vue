<template>
  <div class="product">
    <button @click="removeProduct"></button>
    <img :src="product.img" class="product__img" />
    <div class="product__info">
      <h2>{{ product.title }}</h2>
      <p>{{ product.body }}</p>
      <span>{{ product.price }} руб.</span>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
  methods: {
    removeProduct() {
      this.$emit("remove", this.product);
    },
  }
};
</script>
<style lang="scss" scoped>
.product {
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  position: relative;

  &__info {
    padding: 16px;
    box-sizing: border-box;
  }

  &__img {
    width: 332px;
    height: 200px;
    object-fit: contain;

    @media (max-width: 695px) {
      width: 100%;
    }
  }

  h2 {
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 25px;
    color: #3f3f3f;
  }

  p {
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 20px;
    color: #3f3f3f;
  }

  span {
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    line-height: 30px;
    color: #3f3f3f;
  }

  button {
    background: url("../assets/delete.svg") no-repeat center;
    position: absolute;
    top: -10px;
    right: -10px;
    cursor: pointer;
    border: none;
    width: 32px;
    height: 32px;
    border-radius: 10px;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);

    &:hover {
      opacity: 0.8;
    }
  }
}
</style>
