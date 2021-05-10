<template>
  <div class="root">
    <p>Mostrando {{ filteredTitles.length }} resultados para "{{ query }}"</p>
    <ul>
      <li v-for="title in filteredTitles" :key="title.Page">
        {{ title.Name }}
      </li>
    </ul>
  </div>
</template>

<script>
import titles from "../post-data.json";
import { computed } from "vue";
export default {
  props: {
    query: String,
  },
  setup(props, context) {
    const filteredTitles = computed(() => {
      return titles.filter((s) =>
        s.Name.toLowerCase().includes(props.query.toLowerCase())
      );
    });
    return {
      filteredTitles,
    };
  },
};
</script>

<style scoped>
.root {
  width: 50%;
  margin: 0 auto;
}

.root p {
  text-align: right;
  font-size: 0.7em;
  margin: 0;
}

ul {
  list-style: none;
  width: 50px 0;
  padding: 0;
  background-color: #ffffff;
  border-radius: 5px;
  border: 1px solid #4caf50;
}

li {
  text-align: left;
  padding: 20px;
  border-bottom: 1px solid #4caf50;
}

li:nth-last-of-type(1) {
  border-bottom: none;
}
</style>
