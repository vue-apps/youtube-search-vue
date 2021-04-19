<template>
  <li
    @click="onVideoSelect"
    class="list-group-item media d-flex flex-column flex-md-row"
  >
    <img :src="thumbnailUrl" class="mr-3" />
    <div class="media-body">
      <h5 class="mt-0 mb-1">{{ video.snippet.title }}</h5>
      <small>{{ video.snippet.description }}</small>
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
  methods: {
    onVideoSelect() {
      this.$emit('videoSelect', this.video);
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

@media (min-width: 500px) {
  img {
    width: 100%;
  }
}

@media (min-width: 768px) {
  img {
    width: 20%;
  }
}
</style>
