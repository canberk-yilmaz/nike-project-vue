<template>
  <b-nav-item class="navCart">
    <button><i class="fas fa-shopping-cart"></i></button>
    <div class="total-quantity">1</div>
    <div class="cart-dropdown">
      <ul class="cart_dropdown__list">
        <li>Product</li>
      </ul>
    </div>
  </b-nav-item>
</template>

<script>
export default {
  name: "ShoppingCart",
};
</script>

<style scoped>
.total-quantity {
    font-size: 12px;
    background: #000000;
    color: #fff;
    padding: 0 5px;
    vertical-align: top;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: row;
}

i {
  font-size: 1rem;
}
</style>