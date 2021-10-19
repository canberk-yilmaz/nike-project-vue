<template>
  <div class="d-flex flex-row justify-content-around align-items-center">
    <b-card
      :title="product.title"
      :img-src="product.images[0]"
      img-alt="product.title"
      img-top
      tag="article"
      style="max-width: 20rem"
      class="mb-4"
    >
      <b-card-text>
        {{ product.summary }}
      </b-card-text>

      <b-button href="#" variant="primary">Add To Cart</b-button>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["product"],
};
</script>

<style scoped>
h1 {
  margin: 5px;
}

.card-img-top {
  width: 316.99px;
  height: 316.99px;
  overflow: hidden;
  border: 5px solid black;
}
</style>
