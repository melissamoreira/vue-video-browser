<template>
  <div id="app" class="container">
    <search-bar @termChange="onTermChange"></search-bar>
    <div class="row">
      <video-details :video="selectedVideo" />
      
      <video-list 
        @videoSelect="onVideoSelect"
        :videos="videos"
        ></video-list>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetails from './components/VideoDetails';

const API_KEY = 'AIzaSyCqolOXu_qCfi_5q5LXfe5HF9wBpQ2hg2g';

export default {
  name: 'app',
  components: {
    SearchBar,
    VideoList,
    VideoDetails
  },
  data() {
    return { videos: [], selectedVideo: null };
  },
  methods: {
    
    //Passing the video received by the inner components to our selectedVideo data prop
    onVideoSelect(video) {
      this.selectedVideo = video;
    },

    onTermChange (searchTerm) { 
      
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
            //q = query
        }
      }).then(response => {
        this.videos = response.data.items;
      });

    }
  }
}
</script>

<style lang="stylus">
</style>
