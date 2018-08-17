<template>
    <ul class="list-group">
        <video-list-item 
            v-for="video in videos"
            :video="video"  
            :key="video.etag"
            @videoSelect="onVideoSelect"
        ></video-list-item>

    </ul>    
</template>

<script>
import VideoListItem from './VideoListItem';

export default {
    name: 'VideoList',
    components: {
        VideoListItem
    },
    props: ['videos'],
    methods: {

        //The 'onVideoSelect' method inside VideoList component receives a param 'video', that is the video passed by VideoListItem. That's why it hasn't the 'this' keyword.
        
        onVideoSelect(video) {
            this.$emit('videoSelect', video);
        }
    }
}
</script>

<style lang="stylus" scoped>

</style>
