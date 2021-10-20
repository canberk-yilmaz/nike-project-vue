<template>
  <div class="d-flex">
    <b-nav pills class="d-flex justify-content-center align-items-center">
      <b-nav-item active>All Products</b-nav-item>
      <b-nav-item>Women</b-nav-item>
      <b-nav-item>Men</b-nav-item>
      <ShoppingCart />
    </b-nav>
  </div>
</template>

<script>
import ShoppingCart from "./ShoppingCart.vue";

export default {
  name: "Navbar",
  components: {
    ShoppingCart,
  },
};
</script>

<style scoped>
* {
  margin: 5px;
  padding: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #111;
  font-size: 2rem;
  font-weight: bold;
}

.nav-pills .nav-link.active,
.nav-pills .show > .nav-link {
  background-color: transparent;
  color: #111;
}

li.nav-item {
  width: 200px;
}
</style>
