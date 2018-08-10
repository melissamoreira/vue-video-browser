<template>
  <div id="app">
    <search-bar @termChange="onTermChange"></search-bar>
    <video-list></video-list>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';

const API_KEY = 'AIzaSyCqolOXu_qCfi_5q5LXfe5HF9wBpQ2hg2g';

export default {
  name: 'app',
  components: {
    SearchBar,
    VideoList
  },
  methods: {
    onTermChange (searchTerm) { 
      
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
            //q = query
        }
      }).then(response => console.log(response));

    }
  }
}
</script>

<style lang="stylus">
</style>
