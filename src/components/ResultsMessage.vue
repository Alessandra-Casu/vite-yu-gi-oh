<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="results-message">
    Found {{ store.characterList.lenght }} characters
  </div>
</template>

<style lang="scss" scoped>
.results-message {
  padding-top: 2em;
  padding-bottom: 2em;
  text-align: center;
  font-weight: bold;
}
</style>
