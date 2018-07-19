<template>
  <div class="hello">
    <ul>
      <li v-for="commit in commits" :key="commit.name">
         <p>{{ commit.sha }} - Build: {{ commit.build }} </p>
         <p>by {{ commit.owner }} at {{ commit.createdAt }} </p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Commits',
  data() {
    return {
      commits: [],
      commit: {sha: "",build: "",owner: "",createdAt: 0}
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
