<template>
  <div class="container">
    <div>
      </div><div class="col-md-6">
      <img
        :src="product.images[0]"
        :alt="product.title"
        :img-alt="product.title"
      />
      <div class="size-select d-flex">
        <div class="shoe-size mr-1" v-for="(n, index) in 8" :key="index">
          {{ n + 4 }}
        </div>
      </div>
    </div>
    <div class="desc col-6">
      <h4>{{ product.category }}'S RUNNING SHOE</h4>
      <h3>{{ product.title }}</h3>
      <h3>${{ product.price }}</h3>
      <h3>{{ product.rating }}</h3>
      <h4 v-if="product.stock > 5">In Stock</h4>
      <h4 v-else-if="product.stock > 1">Last Few Pieces!</h4>
      <h4 v-else-if="product.stock > 0">Last One!</h4>
      <h4 v-else>Out of Stock</h4>
      <p>{{ product.summary }}</p>
      <div>
        <span
          v-for="(item, i) in product.rating"
          class="fa fa-star checked"
          :key="i"
        />
        <span
          v-for="(item, i) in 5 - product.rating"
          class="fa fa-star"
          :key="'star' - i"
        />
        <div class="cta">
          <button class="cta-btn" @click="addToCart(product)">
            <b-badge variant="light">Add To Cart</b-badge>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["product"],
  methods: {
    addToCart(value) {
      this.$emit("addToCart", value);
    },
  },
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
.cta-btn {
  width: 100%;
}
.desc {
  text-align: start;
  align-items: start;
  margin-left: 1rem;
  margin-top: 1rem;
  overflow: hidden;
}

.fa-star {
  color: #d8cccc;
}

.checked {
  color: #2c3e50;
}
.container {
  background: #f6f6f6;
}
</style>
