<template>
  <div id="app">
    <Navbar />
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->

    <b-row class="d-flex align-items-center justify-content-center">
      <ProductCard
        :product="product"
        v-for="(product, i) in productList"
        :key="i"
        class="col"
      />
    </b-row>
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
            "The Nike React Infinity Run Flyknit 2 By You continues to help keep you running. A refreshed upper uses Flywire technology that combines with Flyknit for support and breathability where you need it. The high foam heights provide soft responsiveness and long-lasting comfort.",
          price: 140,
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
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/1.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/2.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/3.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/4.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/5.png?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pearlPink/6.jpg?raw=true",
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
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/2.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/3.jpg?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/4.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/5.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/pink-2/6.webp?raw=true",
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
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/2.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/3.jpg?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/4.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/5.webp?raw=true",
            "https://github.com/canberk-yilmaz/nike-project-vue/blob/main/src/img/white/6.webp?raw=true",
          ],
          size: [5, 6, 7, 8, 9, 10, 11, 12],
          stock: 10,
          category: "MEN",
          rating: 5,
        },
      ],
      catClass: {
        MEN: "blue",
        WOMEN: "pink"
      },
      cart: [],
    };
  },
  computed: {
    cartItemCount() {
      let count = 0;
      for (let i = 0; i < this.cart.length; i++) {
        count += this.cart[i].count;
      }
      return count;
    },
  },
  methods: {
    productCal(val) {
      let index = this.cart.findIndex((el) => el.title === val.value.title);
      switch (val.type) {
        case "add":
          if (index >= 0) {
            this.basket[index].count++;
          } else {
            this.cart.unshift({ ...val.value, count: 1 });
          }
          break;
        case "+":
          this.basket[index].count++;
          break;
        case "-":
          if (this.basket[index].count > 1) {
            this.basket[index].count--;
          } else {
            this.cart.splice(index, 1);
          }
          break;
        case "del":
          this.cart.splice(index, 1);
          break;
        default:
      }
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
  background: #f6f6f6;
  height: 100vh;
}

.pink {
  color: pink;
}

.blue {
  color: blue;
}


</style>
