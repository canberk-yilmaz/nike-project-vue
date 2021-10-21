<template>
  <div class="container">
    <div>
      <img
        :src="product.images[0]"
        :alt="product.title"
        :img-alt="product.title"
      />
      <div class="size-select" style="display: flex">
        <div class="shoe-size mr-1" v-for="(n, index) in 8" :key="index">
          {{ n + 4 }}
        </div>
      </div>
    </div>
    <div class="desc">
      <h4>{{ product.category }}'S RUNNING SHOE</h4>
      <h3>{{ product.title }}</h3>
      <h3>${{ product.price }}</h3>
      <h4 v-if="product.stock > 5">In Stock</h4>
      <h4 v-else-if="product.stock > 1">Last Few Pieces!</h4>
      <h4 v-else-if="product.stock > 0">Last One!</h4>
      <h4 v-else>Out of Stock</h4>
      <p>{{ product.summary }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["product"],
};
</script>

<style scoped>
* {
  background: #f6f6f6;
}

h1 {
  margin: 5px;
}

img {
  width: 316.99px;
  height: 316.99px;
  overflow: hidden;
}

.container {
  border: 2px solid black;
  border-radius: 1rem;
  box-shadow: 0px 0px 8px 8px #686565;
  height: 34rem;
  display: flex;
  margin: 0 3rem 6rem 3rem;
  max-width: 1000px;
}

.size-select {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: center;
  overflow: visible;
}
.shoe-size {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  border: 3px solid black;
  color: black;
  font-weight: 800;
}

.desc {
  text-align: start;
  align-items: start;
  margin-left: 1rem;
  margin-top: 1rem;
  overflow: hidden;
}

* {
  background: #f6f6f6;
}
</style>
