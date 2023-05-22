<script>
export default {
  props: {
    characterData: Object,
  },
};
</script>

<template>
  <div class="card">
    <img
      :src="characterData.card_images[0].image_url_small"
      :alt="characterData.name"
    />
    <h2>{{ characterData.name }}</h2>
    <div class="type">{{ characterData.type }}</div>
  </div>
</template>

<style lang="scss">
.card {
  padding: 2rem 1rem;
  gap: 1rem solid white;
  background-color: #d48f38;
}
img {
  max-width: 100%;
}
</style>
