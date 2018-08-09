<template>
  <div class="searchbar">
   <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {  
    onInput: (event) => {
      console.log(event.target.value);
    }
  }
};
</script>


<style lang="stylus" scoped>

</style>
