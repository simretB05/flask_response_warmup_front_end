<template>
  <div id="app">
    <post-pokemon></post-pokemon>
    <get-pokemon></get-pokemon>

  </div>
</template>

<script>
import PostPokemon from './components/PostPokemon.vue';
import GetPokemon from '@/components/GetPokemon.vue';
export default {
  components: {
    GetPokemon,
    PostPokemon
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
