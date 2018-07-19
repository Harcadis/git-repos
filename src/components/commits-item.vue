<template>
  <div class="commit-item">
    <p> {{ commit.sha }} - build: {{ commit.commit.message }} </p>
    <p> by {{ commit.commit.author.name }} at {{ commit.commit.author.date }} </p>
  </div>
</template>

<script>
export default {
  name: 'commits',
  props: [ 'commit' ],
  data() {
    return {
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
