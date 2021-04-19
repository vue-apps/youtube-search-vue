<template>
  <div class="container">
    <SearchBar @searchQuery="onSearchQuery" />
    <VideoList @videoSelect="showVideo" :videos="videos"></VideoList>
  </div>
</template>

<script>
import SearchBar from './components/searchBar';
import VideoList from './components/videoList';
import axios from 'axios';
const API_KEY = 'AIzaSyAdObW29k_2F2ic1BZMg7_OgP011wdxAdM';

export default {
  data() {
    return { videos: [] };
  },
  name: 'App',
  components: {
    SearchBar,
    VideoList,
  },
  methods: {
    onSearchQuery(queryString) {
      axios
        .get('https://www.googleapis.com/youtube/v3/search', {
          params: {
            key: API_KEY,
            type: 'video',
            part: 'snippet',
            q: queryString,
          },
        })
        .then((res) => {
          // console.log(res);
          this.videos = res.data.items;
        });
    },
    showVideo(video) {
      console.log(video);
    },
  },
};
</script>
