<template>
  <ul>
    <VideoListItem v-for="video in videos" :key="video.id" v-bind:video="video">
    </VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from './videoListItem';

export default {
  name: 'videoList',
  components: {
    VideoListItem,
  },
  props: {
    videos: Array,
  },
};
</script>

<style></style>
