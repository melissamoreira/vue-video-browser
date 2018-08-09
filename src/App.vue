<template>
  <div id="app">
    <search-bar></search-bar>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';

export default {
  name: 'app',
  components: {
    SearchBar
  }
}
</script>

<style lang="stylus">

#app
  font-family 'Avenir', Helvetica, Arial  
</style>
