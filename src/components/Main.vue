<template>
  <div>
    <h1>proyecto {{proyecto}} Cmmmits from {{ userName }}</h1>
    <h2>Ramas</h2>
    <ul>
        <li v-for="branch in branches" :key="branch.name">
            {{ branch.name }} <input type="radio">
        </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

const token = '?access_token=159a5ae1f09970af4ddb1916295a9f4eb4d52269'
const url = 'https://github.com/repos/BorjaZarco/Full-Stack_TwitterBackEnd/branches'+token

export default {
  name: 'Main',
  data() {
    return {
      userName:"BorjaZarco",
      proyecto: "Full-Stack_TwitterBackEnd",
      branches: [
          {
              name: "master",
              Commit: {
                  sha: "",
                  ur: "soy el mas guay jugando al pingpong"
              } 
          },
          {
              name: "dev",
              Commit: {
                  sha: "",
                  ur: "soy el mas guay jugando al pingpong"
              } 
          }
      ],
      commitsURL: []
    }
  },
  created() {
    // axios.get(url).then(res => (branchs = res)).catch(error)
  },
  components: {
    Commits
  },
  methods: {
    getRepo(){

    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>