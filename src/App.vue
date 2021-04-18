<template>
  <div>
    <SearchBar @searchQuery="onSearchQuery" />
  </div>
</template>

<script>
import SearchBar from './components/searchBar';
import axios from 'axios';
const API_KEY = 'AIzaSyBQiEJ1NRjPoMKeTtkzCQetScCg5KUucJ4';

export default {
  name: 'App',
  components: {
    SearchBar,
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
          console.log(res.data);
        });
    },
  },
};
</script>
