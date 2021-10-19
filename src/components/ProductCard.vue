<template>
  <div>
    <div>
      <b-card
        :title="product.title"
        :img-src="product.images[0]"
        img-alt="product.title"
        img-top
        tag="div"
        style="max-width: 20rem"
      >
        <b-card-text>
          {{ product.summary }}
        </b-card-text>

        <b-button href="#" variant="primary">Add To Cart</b-button>
      </b-card>
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
h1 {
  margin: 5px;
}

.card-img-top {
  width: 316.99px;
  height: 316.99px;
  overflow: hidden;
}

.card {
  background: none;
  border: none;
}
</style>
