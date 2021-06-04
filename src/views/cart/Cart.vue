<template>
  <div class="cart">
    <!-- 商品导航 -->
    <nav-bar class="nav-bar">
      <div slot="center">购物车({{length}})</div>
    </nav-bar>
    <!-- 商品的列表 -->
    <cart-list></cart-list>
    <!-- 底部汇总 -->
    <cart-buttom-bar></cart-buttom-bar>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
import CartList from "./childCart/CartList";
import CartButtomBar from "./childCart/CartButtomBar";

import { mapGetters } from "vuex";

export default {
  name: "Cart",
  components: {
    NavBar,
    CartList,
    CartButtomBar,
  },
  computed: {
    // ...mapGetters(["cartLength", "cartList"]),
    ...mapGetters({
      length: "cartLength",
    }),
  },
};
</script>

<style scoped>
.cart {
  height: 100vh;
}
.nav-bar {
  background-color: var(--color-tint);
  color: #fff;
}
</style>
