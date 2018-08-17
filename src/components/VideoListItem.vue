<template>
    <li class="list-group-item media"
        @click="onVideoSelect">
    
        <!-- Call the method onVideoSelect at the click event -->

        <img :src="thumbnailUrl" alt="" class="mr-3">

        <div class="media-body">
            {{ video.snippet.title }}
        </div>

    </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: ['video'],
    computed: {
        thumbnailUrl() {
            return this.video.snippet.thumbnails.default.url;
        }
    },
    methods: {
        onVideoSelect() {
            this.$emit('videoSelect', this.video);
                //First param is the event, second is the prop
        }
    }
}
</script>
<style lang="stylus" scoped>
.media
    display flex
    cursor pointer
    &:hover 
        background-color #eee
</style>

