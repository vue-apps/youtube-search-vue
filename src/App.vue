<template>
  <div class="container">
    <SearchBar @searchQuery="onSearchQuery" />
    <div class="row">
      <VideoDetail :video="selectedVideo" />
      <VideoList @videoSelect="showVideo" :videos="videos" />
    </div>
  </div>
</template>

<script>
import SearchBar from './components/searchBar';
import VideoList from './components/videoList';
import VideoDetail from './components/videoDetail';
import axios from 'axios';
const API_KEY = 'AIzaSyAdObW29k_2F2ic1BZMg7_OgP011wdxAdM';

export default {
  data() {
    return { videos: [], selectedVideo: null };
  },
  name: 'App',
  components: {
    SearchBar,
    VideoList,
    VideoDetail,
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
      this.selectedVideo = video;
    },
  },
};
</script>
