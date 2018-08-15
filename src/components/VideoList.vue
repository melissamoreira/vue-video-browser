<template>
    <ul>
        <video-list-item 
            v-for="video in videos"
            :video="video"  
            :key="video.etag"
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
    props: ['videos']
}
</script>

<style lang="stylus" scoped>

</style>
