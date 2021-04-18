<template>
  <ul>
    <VideoListItem />
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
