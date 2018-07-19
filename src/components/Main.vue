<template>
  <div>
    <h2> Proyecto {{proyect}} Commits from {{ username }}</h2>
    <h3>Ramas </h3>
    <ul>
        <li v-for="branch in branches" :key="branch.name">
            {{ branch.name }} <input :checked="isFirst() === true" :id="branch.commit.sha" :value="[branch.name, branch.commit.sha]" type="radio" v-model="picked" >
        </li>
    </ul>
    <commitList :sha="picked[1]" :username="username" :proyect="proyect" :branch="picked[0]"></commitList>
  </div>
</template>

<script>
import axios from 'axios'
import commitList from './commits-list'

const username = "YuniorGlez";
const proyect = "express-mongoose-jade-crm";
const token = '?access_token=520389b369f0441ba88f20e86da46d1f68039a9a'
const url = 'https://api.github.com/repos/'+username+'/'+proyect+'/branches'+token



export default {
  name: 'Main',
  data() {
    return {
      bool: true,
      username: username,
      proyect: proyect,
      picked: "",
      branches: [],
    }
  },
  created() {
    axios.get(url)
      .then(res => {
        this.branches = res.data
        })
      .catch(error => console.log(error))
  },
  components: {
    commitList
  },
  methods: {
    isFirst () {
      if(this.bool) {
        this.bool = false;
        return true;
      }
      return false;
    }
  }
};
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  list-style-type: none;
  display: flex;
  align-items: center;
  justify-content: center;
}

</style>