<template>
    <li>
        {{ video.snippet.title }}
    </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: ['video'] //Props that will be passed by the parent
}
</script>
