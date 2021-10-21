<template>
  <div class="d-flex box">
    <b-nav pills class="d-flex justify-content-center align-items-center">
      <b-nav-item active>All Products</b-nav-item>
      <b-nav-item>Women</b-nav-item>
      <b-nav-item>Men</b-nav-item>
      <!-- <b-nav-item>
        <i class="fas fa-shopping-bag"></i>
      </b-nav-item> -->
    </b-nav>
    <b-dropdown id="dropdown-dropright" dropright>
      <template #button-content>
        <span class="m-2 fas fa-shopping-bag"></span>
        <b-badge>{{ cart.length }}</b-badge>
      </template>
      <b-dropdown-item v-for="(item, index) in cart" :key="index">
        <div>
          {{ item.title }} - ${{ item.price * item.counter }}
          <b-button @click="deleteItem" variant="danger">x</b-button>
        </div>
      </b-dropdown-item>
    </b-dropdown>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  props: ["cart"],
  methods: {
    deleteItem(i) {
      this.cart.splice(i, 1);
    },
  },
};
</script>

<style scoped>
* {
  margin: 0.5rem;
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

.box {
  border-bottom: 0.2rem solid #111;
  margin-bottom: 2.5rem;
}

i {
  font-size: 2rem;
  color: #111;
}

.badge {
  background-color: #f1f1f1;
}
</style>
