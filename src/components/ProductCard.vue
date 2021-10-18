<template>
  <div>
    <div>
      <b-card
        title="Card Title"
        img-src="../img/black/1.webp"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="mb-2"
      >
        <b-card-text>
          Some quick example text to build on the card title and make up the
          bulk of the card's content.
        </b-card-text>

        <b-button href="#" variant="primary">Go somewhere</b-button>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
};
</script>

<style scoped>
h1 {
  margin: 5px;
}
</style>
