<template>
  <ul class="list-group">
    <VideoListItem
      @videoSelect="onVideoSelect"
      v-for="video in videos"
      :key="video.id.videoId"
      :video="video"
    >
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
  methods: {
    onVideoSelect(video) {
      this.$emit('videoSelect', video);
    },
  },
};
</script>

<style></style>
