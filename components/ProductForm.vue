<template>
  <div class="addForm">
    <form @submit.prevent>
      <div class="input__title">
        <h4 class="productTitle title">Наименование товара</h4>
      </div>
      <input v-model="product.title" class="input" type="text" placeholder="Введите наименование товара" />
      <p class="productTitle">Описание товара</p>
      <textarea v-model="product.body" class="about" type="text" placeholder="Введите описание товара" />
      <h4 class="productTitle img">Ссылка на изображение товара</h4>
      <input v-model="product.img" class="input" type="text" placeholder="Введите ссылку" />
      <h4 class="productTitle price">Цена товара</h4>
      <input v-model="product.price" class="price" type="text" placeholder="Введите цену" />
      <button @click="createProduct">Добавить товар</button>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      product: {
        title: "",
        body: "",
        img: "",
        price: "",
      },
    };
  },
  methods: {
    createProduct() {
      this.product.id = Date.now();
      this.$emit("create", this.product);
      this.product = {
        title: "",
        body: "",
        img: "",
        price: "",
      };
    },
  },
};
</script>
<style lang="scss" scoped>
.addForm {
  min-width: 24%;

  @media screen and (max-width: 1024px) {
    min-width: 28%;
  }

  @media screen and (max-width: 768px) {
    min-width: 36%;
  }

  @media (min-width: 696px) {
    display: block;
  }

  @media (max-width: 695px) {
    display: none;
  }
}

h4 {
  margin: 0;
}

.productTitle {
  font-family: "Source Sans Pro";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 13px;
  letter-spacing: -0.02em;
  color: #49485e;
  position: relative;

  &.title {
    &::after {
      position: absolute;
      top: 0;
      left: 95px;
      background: url("../assets/dot.svg") no-repeat;
      color: white;
      content: "o";
    }
  }

  &.img {
    &::after {
      position: absolute;
      top: 0;
      left: 133px;
      background: url("../assets/dot.svg") no-repeat;
      color: white;
      content: "o";
    }
  }

  &.price {
    &::after {
      position: absolute;
      top: 0;
      left: 53px;
      background: url("../assets/dot.svg") no-repeat;
      color: white;
      content: "o";
    }
  }
}

form {
  width: 100%;
  background: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  padding: 24px;
  box-sizing: border-box;
}

input {
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  border: none;
  width: 100%;
  height: 36px;
  margin-bottom: 16px;

  &::placeholder {
    font-family: "Source Sans Pro";
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 15px;
    color: #b4b4b4;
    padding: 10px 16px;
    position: absolute;
    top: 0;
  }

  &:focus {
    outline: none;
  }

  &.price {
    margin-bottom: 24px;
  }
}

textarea {
  min-height: 108px;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  border: none;
  width: 100%;
  resize: none;
  box-sizing: border-box;
  margin-bottom: 16px;

  &:focus {
    outline: none;
  }

  &::placeholder {
    font-family: "Source Sans Pro";
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 15px;
    color: #b4b4b4;
    padding: 10px 16px;
  }
}

button {
  background: #eeeeee;
  border-radius: 10px;
  border: none;
  width: 100%;
  height: 36px;
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  line-height: 15px;
  text-align: center;
  letter-spacing: -0.02em;
  color: #b4b4b4;
  cursor: pointer;
}
</style>
