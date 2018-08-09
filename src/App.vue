<template>
  <div id="app">
    <search-bar @termChange="onTermChange"></search-bar>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';

export default {
  name: 'app',
  components: {
    SearchBar
  },
  methods: {
    onTermChange (searchTerm) {
      console.log(searchTerm);
    }
  }
}
</script>

<style lang="stylus">
</style>
