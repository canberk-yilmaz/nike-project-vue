<template>
  <div id="app">
    <Navbar :cart="cart" />
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <div class="contain">
      <b-row
        class="d-flex align-items-center justify-content-center"
        id="shoe-box"
      >
        <ProductCard
          :product="product"
          v-for="(product, i) in productList"
          :key="i"
          class="col"
          @addToCart="addToCart"
        />
      </b-row>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import ProductCard from "./components/ProductCard.vue";

export default {
  name: "App",
  components: {
    Navbar,
    ProductCard,
  },
  data() {
    return {
      productList: [
        {
          title: "Nike React Infinity Run Flyknit 2 By You",
          color: "Black",
          summary:
            "The Nike React Infinity Run Flyknit 2 By You continues to help keep you running. A refreshed upper uses Flywire technology that combines with Flyknit for support and breathability where you need it.",
          price: 140,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/black/1.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "MEN",
          rating: 4,
        },
        {
          title: "Nike Epic React Flyknit 2",
          color: "Pearl Pink",
          summary:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam, quam.",
          price: 150,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/1.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "WOMEN",
          rating: 5,
        },
        {
          title: "Nike Epic React Flyknit 3",
          color: "Pink",
          summary: "Lorem ipsum dolor, sit amet consectetur adipisicing.",
          price: 145,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/1.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "WOMEN",
          rating: 4,
        },
        {
          title: "Nike Epic React Flyknit 4",
          color: "Blue",
          summary: "Lorem ipsum dolor, sit amet consectetur adipisicing.",
          price: 155,
          images: [
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/1.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "MEN",
          rating: 5,
        },
      ],
      catClass: {
        MEN: "blue",
        WOMEN: "pink",
      },
      cart: [],
      alert: false,
      counter: 0,
    };
  },
  methods: {
    addToCart(e) {
      let addedBefore = this.cart.filter((item) => item.title === e.title);
      if (addedBefore) {
        let index = this.cart.findIndex((item) => item.title === e.title);
        this.cart[index].counter++;
        this.cart.push({ ...e, counter: addedBefore + 1 });
      } else {
        this.cart.push({ ...e, counter: 1 });
      }
      //this.cart.push(e);
      console.log(this.cart);
    },
  },
};
</script>

<style>
#app {
  font-family: "Noto Sans Mono", monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}

.pink {
  color: pink;
}

.blue {
  color: blue;
}

* {
  background: #f1f1f1;
}

.contain {
  max-width: 96rem;
  margin-left: auto;
  margin-right: auto;
}

.btn-secondary {
  background: #f1f1f1;
  color: #2c3e50;
  border: none;
}

.btn.dropdown-toggle.btn-secondary:after {
  content: none;
}

.dropdown-item {
  font-size: 1rem;
}
</style>
