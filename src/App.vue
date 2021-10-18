<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">Logo Here</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Careers</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Contact</a>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input
            class="form-control mr-sm-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">
            Search
          </button>
        </form>
      </div>
    </nav>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <b-row class="d-flex justify-content-center">
      <ProductCard v-for="(item, i) in productList" :key="i" class="col" />
    </b-row>
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
          title: "Title 1",
          summary:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam, quam.",
          rating: 4,
          price: 10,
        },
        {
          title: "Title 2",
          summary: "Lorem ipsum dolor sit amet.",
          rating: 3,
          price: 20,
        },
        {
          title: "Title 3",
          summary: "Lorem ipsum dolor, sit amet consectetur adipisicing.",
          price: 5,
        },
        {
          title: "Title 4",
          summary: "Lorem ipsum dolor, sit amet consectetur adipisicing.",
          price: 5,
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
  margin-top: 60px;
}
</style>
