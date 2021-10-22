<template>
  <div id="app">
    <nav class="d-flex box mb-5 sticky-top">
      <b-nav pills class="d-flex justify-content-center align-items-center">
        <b-nav-item active>All Products</b-nav-item>
        <b-nav-item class="pink">Women</b-nav-item>
        <b-nav-item>Men</b-nav-item>
        <!-- <b-nav-item>
        <i class="fas fa-shopping-bag"></i>
      </b-nav-item> -->
      </b-nav>
      <b-dropdown id="dropdown-dropright" dropright>
        <template #button-content>
          <span class="m-2 fas fa-shopping-bag"></span>
          <b-badge>{{ cartTotal }}</b-badge>
        </template>
        <b-dropdown-item v-for="(item, index) in cart" :key="index">
          <div v-if="item.count > 0">
            <div>
              {{ item.title }}
              </div>
              <div>Qty:{{ item.count }} - Total Price: ${{
              item.price * item.count }}
            </div>
            <span>
            <b-button
              class="mr-2"
              v-if="item.count > 1"
              @click.stop.prevent="item.count--"
              variant="dark"
              >-</b-button
            >
            <b-button
              class="mr-2"
              v-else-if="(item.count = 1)"
              @click.stop.prevent="deleteItem(index)"
              variant="dark"
              >-</b-button
            >
            <b-button
              class="mr-2"
              @click.stop.prevent="item.count++"
              variant="dark"
              >+</b-button
            >
            <b-button @click.stop.prevent="deleteItem(index)" variant="danger"
              >x</b-button
            >
            </span>
          </div>
        </b-dropdown-item>

        <b-dropdown-item v-show="cart.length === 0">
          Oh No! Your Cart Is Empty :(
        </b-dropdown-item>
      </b-dropdown>
    </nav>
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
import ProductCard from "./components/ProductCard.vue";

export default {
  name: "App",
  components: {
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
      let addedBefore = this.cart.filter(
        (item) => item.title === e.title
      ).length;

      if (addedBefore) {
        let index = this.cart.findIndex((item) => item.title === e.title);
        console.log(index);
        this.cart[index].count++;
      } else {
        this.cart.push({ ...e, count: 1 });
      }
      console.log(this.cart);
    },
    deleteItem(i) {
      this.cart.splice(i, 1);
    },
  },
  computed: {
    cartTotal() {
      let count = 0;
      for (let i = 0; i < this.cart.length; i++) {
        count += this.cart[i].count;
      }
      return count;
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

.nav-pills .nav-link.active,
.nav-pills .show > .nav-link {
  background-color: transparent;
  color: #111;
}

li.nav-item {
  width: 200px;
}

.box {
  border-bottom: 0.2rem solid #2c3e50;
  margin-bottom: 2.5rem;
  margin: 0.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #2c3e50;
  font-size: 2rem;
  font-weight: bold;
}

.fa-shopping-bag.badge {
  background-color: #f1f1f1;
  color: #111;
  font-size: 2rem;
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
.btn {
  font-size: 2rem;
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

.nav-link {
  color: #2c3e50;
}
</style>
