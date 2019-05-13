<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <VPaginator :list="users" :rows="6" :fields="['id', 'name', 'username']"/>
  </div>
</template>

<script>
import VPaginator from './components/VPaginator.vue'

export default {
  name: 'app',

  components: {
    VPaginator
  },

  data () {
    return {
      users: []
    }
  },

  created () {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(response => response.json())
      .then(json => {
        this.users = json
      })
  }
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Ubuntu");

#app {
  font-family: "Ubuntu", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
