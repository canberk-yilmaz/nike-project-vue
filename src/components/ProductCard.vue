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
      <h2>{{ product.title }}</h2>
      <h2>${{ product.price }}</h2>
      <p>{{ product.summary }}</p>
      <h4>Stock: {{ product.stock }}</h4>
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
  border: 1px solid black;
  height: 750px;
  display: flex;
  align-items: center;
  margin-left: 150px;
  margin-right: 150px;
  margin: 0px 150px 150px 150px;
  max-width: 723px;
}

.size-select {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: center;
  overflow:visible
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
}
</style>
