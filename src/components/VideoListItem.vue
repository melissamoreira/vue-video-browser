<template>
    <li class="media">

        <!-- Passing just the function that returns the thumb in the src attr -->
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
                //When referencing a prop inside a function, use 'this'
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

