<template>
  <div class="hello">
    <h2>{{this.username}}/{{this.proyect}}@{{this.branch}}</h2>
    <ul>
      <div v-for="commit in commits" :key="commit.name">
        <commitItem :commit="commit"></commitItem>
      </div>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
import commitItem from './commits-item'

const token = '?access_token=520389b369f0441ba88f20e86da46d1f68039a9a'
const url = 'https://api.github.com/repos/YuniorGlez/express-mongoose-jade-crm/commits'+token

export default {
  name: 'commits',
  props: ["sha", "username", "proyect", "branch"],
  data() {
    return {
      commits: []
    };
  },
  components: {
    commitItem
  },
  watch: {
    sha () {
      axios.get(url+'&sha='+this.sha)
      .then(res => {
        this.commits = res.data
        })
      .catch(error => console.log(error))
    }
  }
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
