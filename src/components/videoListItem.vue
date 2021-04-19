<template>
  <li class="list-group-item media d-flex flex-column flex-md-row">
    <img :src="thumbnailUrl" class="mr-3" />
    <div class="media-body">
      <h5 class="mt-0 mb-1">{{ video.snippet.title }}</h5>
      {{ video.snippet.description }}
    </div>
  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: {
    video: Object,
  },
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.medium.url;
    },
  },
};
</script>

<style scoped>
li {
  cursor: pointer;
}

li:hover {
  background-color: #eee;
}

@media (max-width: 767px) {
  img {
    width: 100%;
  }
}
</style>
