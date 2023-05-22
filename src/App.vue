<script>
import CharacterCard from "./components/CharacterCard.vue";
import CharacterList from "./components/CharacterList.vue";
import ResultsMessage from "./components/ResultsMessage.vue";
import axios from "axios";
import { store } from "./store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    CharacterList,
    ResultsMessage,
  },
  created() {
    //qui fare la richiesta al'api
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php")
      .then((ajax) => (this.store.characterList = ajax.data.results));
  },
};
</script>

<template>
  <AppHeader>
    <h1>Yu-Gi-Oh Api</h1>
  </AppHeader>
  <main>
    <ResultsMessage></ResultsMessage>
    <CharacterCard></CharacterCard>
    <CharacterList></CharacterList>
  </main>
</template>

<style lang="scss"></style>
