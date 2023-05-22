<script>
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
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((ajax) => (this.store.characterList = ajax.data.data));
  },
};
</script>

<template>
  <h1>Yu-Gi-Oh Api</h1>

  <main>
    <div class="container">
      <ResultsMessage></ResultsMessage>
      <CharacterList></CharacterList>
    </div>
  </main>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.html {
  font-family: "Montserrat", sans-serif;
}

.container {
  margin: 0 auto;
  padding: 1rem;
  max-width: 1000px;
}

h1 {
  text-align: center;
}
</style>
