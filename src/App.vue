<template>
  <div id="app">
    <div class="nav">
    <Navbar />
    <ShoppingCart />
    </div>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <b-row class="d-flex flex-row justify-content-around align-items-center">
      <div class="col-12">
        <ProductCard
          :product="product"
          v-for="(product, i) in productList"
          :key="i"
          class="col"
        />
      </div>
    </b-row>
  </div>
</template>

<script>

import Navbar from "./components/Navbar.vue";
import ProductCard from "./components/ProductCard.vue";
import ShoppingCart from "./components/ShoppingCart.vue";


export default {
  name: "App",
  components: {
    Navbar,
    ShoppingCart,
    ProductCard,
  },
  data() {
    return {
      productList: [
        {
          title: "Nike Epic React Flyknit 1",
          color: "Black",
          summary:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam, quam.",
          rating: 4,
          price: 10,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/black/1.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/black/2.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/black/3.jpg?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/black/4.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/black/5.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/black/6.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "men's running shoes",
        },
        {
          title: "Nike Epic React Flyknit 2",
          color: "Pearl Pink",
          summary: "Lorem ipsum dolor sit amet.",
          rating: 3,
          price: 20,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/1.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/2.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/3.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/4.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/5.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/6.jpg?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "women's running shoes",
        },
        {
          title: "Nike Epic React Flyknit 3",
          color: "Pink",
          summary: "Lorem ipsum dolor, sit amet consectetur adipisicing.",
          price: 5,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/1.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/2.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/3.jpg?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/4.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/5.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/6.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "women's running shoes",
        },
        {
          title: "Nike Epic React Flyknit 4",
          color: "Blue",
          summary: "Lorem ipsum dolor, sit amet consectetur adipisicing.",
          price: 5,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/1.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/2.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/3.jpg?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/4.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/5.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/6.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "men's running shoes",
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
