<template>
  <div class="hello">
    <h1>Hello apollo</h1>
    <p v-for="res in result?.characters.results" :key="res.id">
      <pre>
        {{ res.name }}
      </pre>
    </p>
  </div>
</template>

<script setup>
import { useQuery } from "@vue/apollo-composable";
import gql from "graphql-tag";

import getCharacters from "../graphql/getCharacters.query.gql"

const { result } = useQuery(gql`${getCharacters}`);
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
