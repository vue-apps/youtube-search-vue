<template>
  <div>
    <SearchBar @searchQuery="onSearchQuery" />
    <VideoList :videos="videos"></VideoList>
  </div>
</template>

<script>
import SearchBar from './components/searchBar';
import VideoList from './components/videoList';
import axios from 'axios';
// const API_KEY = 'AIzaSyAdObW29k_2F2ic1BZMg7_OgP011wdxAdM';

export default {
  data() {
    return { videos: ['movie1', 'movie2', 'movie3', 'movie4', 'movie5'] };
  },
  name: 'App',
  components: {
    SearchBar,
    VideoList,
  },
  methods: {
    onSearchQuery(queryString) {
      axios
        .get(
          `https://jsonplaceholder.typicode.com/albums/${queryString}/photos`
        )
        .then((res) => {
          console.log(res);
          this.videos = res.data;
        });
    },
  },
};
</script>
