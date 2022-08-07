<template>
  <header class="header">
    <h1>Добавление товара</h1>
    <nav>
      <button @click="toggleMobileNav" v-show="mobile" class="header__menu" :class="{ 'active': mobileNav }"></button>
      <transition name="mobile-nav">
        <ProductFormMobile v-show="mobileNav" @create="$emit('create', product)" />
      </transition>
    </nav>
    <button class="header__sort"></button>
  </header>
</template>
<script>
import ProductFormMobile from "../components/ProductFormMobile.vue";
export default {
  name: 'header-link',
  components: { ProductFormMobile },
  data() {
    return {
      mobile: null,
      mobileNav: null,
      windowWidth: null,
    };
  },
  created() {
    if (process.browser) {
      window.addEventListener('resize', this.checkScreen);
      this.checkScreen();
    }
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 695) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    }
  }
};
</script>
<style lang="scss" scoped>
.header {
  margin: 0 auto 30px;
  display: flex;
  min-height: 36px;
  width: 100%;
  justify-content: space-between;

  h1 {
    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 35px;
    color: #3F3F3F;

    @media (max-width: 695px) {
      display: none;
    }
  }

  &__menu {
    height: 44px;
    width: 44px;
    background: url("../assets/burger-menu.svg") center no-repeat;
    cursor: pointer;
    transition: .8s ease all;
    border: none;

    &:hover {
      opacity: 0.5;
    }
  }

  &__sort {
    background: #fffefb;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    border-radius: 4px;
    width: 121.49px;
    height: 36px;
    border: none;
  }
}

.active {
  transform: rotate(180deg);
}

.mobile-nav {
  display: block;
}
</style>
