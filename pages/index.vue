<template>
  <div class="main">
    <Header @create="createProduct" />
    <div class="content">
      <ProductForm @create="createProduct" />
      <ProductList :products="products" />
    </div>
  </div>
</template>

<script>
import ProductForm from "../components/ProductForm.vue";
import ProductList from "../components/ProductList.vue";
import Header from "../components/Header.vue";
export default {
  name: "IndexPage",
  components: { ProductForm, ProductList, Header },
  data() {
    return {
      products: [
        {
          id: 1,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 2,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 3,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 4,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 5,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 6,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 7,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 8,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
        {
          id: 9,
          title: "Наименование товара",
          body: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          img: "https://avatars.mds.yandex.net/get-mpic/4338525/img_id1992414260241354018.jpeg/orig",
          price: 10000,
        },
      ],
    };
  },
  methods: {
    createProduct(product) {
      this.products.push(product);
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
