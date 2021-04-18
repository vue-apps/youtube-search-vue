<template>
  <ul>
    VideoList
    {{
      videos.length
    }}
  </ul>
</template>

<script>
export default {
  name: 'videoList',
  props: {
    videos: Array,
  },
};
</script>

<style></style>
