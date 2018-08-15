<template>
  <div class="searchbar">
   <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {  
    onInput (event) {
      this.$emit('termChange', event.target.value);
    }
  }
};
</script> 

<style lang="stylus" scoped>
input
  width 75%

.searchbar
  margin 20px
  text-align center
</style>
