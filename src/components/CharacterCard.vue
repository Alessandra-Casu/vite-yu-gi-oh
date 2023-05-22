<script>
export default {
  props: {
    characterData: Object,
  },
};
</script>

<template>
  <div class="card">
    <img :src="characterData.image" :alt="characterData.name" />
    <h2>{{ characterData.name }}</h2>
    <div class="type">{{ character.type }}</div>
  </div>
</template>

<style lang="scss">
.card {
  padding: 2rem 1rem;
  border: 2px solid black;
}
img {
  max-width: 100%;
}
</style>
