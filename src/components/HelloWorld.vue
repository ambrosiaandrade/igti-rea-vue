<template>
  <div>
    <h3>Filtrar os artigos de LearnVue</h3>
    <input type="text" placeholder="Filtrar a busca" v-model="query" />
    <button @click="reset">Limpar</button>
    <br />
    <search-results :query="query" />
  </div>
</template>

<script>
import { ref } from "vue";
import SearchResults from "./SearchResults.vue";
export default {
  components: {
    SearchResults,
  },
  setup() {
    const query = ref("");
    const reset = (evt) => {
      query.value = "";
    };
    return {
      reset,
      query,
    };
  },
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
    };
  },
};
</script>

<style>
h3 {
  color: #4caf50;
}

input[type="text"] {
  margin-bottom: 20px;
  padding: 10px;
  width: 38%;
  border-top-style: hidden;
  border-right-style: hidden;
  border-left-style: hidden;
  border-bottom-style: groove;
  outline: none;
}

input[type="text"]:focus {
  background: #ecffed;
  border-bottom-style: double;
  border-bottom-color: #4caf50;
}

button {
  margin-left: 2px;
  margin-bottom: 20px;
  padding: 10px;
  width: 10%;
  background-color: #4caf50; /* Green */
  border: none;
  color: white;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}

button:hover {
  cursor: pointer;
}
</style>
