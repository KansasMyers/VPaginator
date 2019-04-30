<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Paginator :list="itens" :rows="6" :fields="['id', 'nome']" />
  </div>
</template>

<script>
import Paginator from './components/Paginator.vue'

export default {
  name: 'app',
  components: {
    Paginator
  },
  data () {
    return {
      itens: [
        { id: 1, nome: 'José Victor' },
        { id: 2, nome: 'Nicholas Victor' },
        { id: 3, nome: 'Dubs Victor' },
        { id: 4, nome: 'Scrach Victor' },
        { id: 5, nome: 'Devil Victor' },
        { id: 6, nome: 'José Victor' },
        { id: 7, nome: 'Nicholas Victor' },
        { id: 8, nome: 'Dubs Victor' },
        { id: 9, nome: 'Scrach Victor' },
        { id: 10, nome: 'Devil Victor' },
        { id: 11, nome: 'José Victor' },
        { id: 12, nome: 'Nicholas Victor' },
        { id: 13, nome: 'Dubs Victor' },
        { id: 14, nome: 'Scrach Victor' },
        { id: 15, nome: 'Devil Victor' },
        { id: 16, nome: 'José Victor' },
        { id: 17, nome: 'Nicholas Victor' },
        { id: 18, nome: 'Dubs Victor' },
        { id: 19, nome: 'Scrach Victor' },
        { id: 20, nome: 'Devil Victor' }
      ]
    }
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
