<template>
  <div>
    <SearchBar @searchQuery="onSearchQuery" />
  </div>
</template>

<script>
import SearchBar from './components/searchBar';
const API_KEY = 'AIzaSyBQiEJ1NRjPoMKeTtkzCQetScCg5KUucJ4';

export default {
  name: 'App',
  components: {
    SearchBar,
  },
  methods: {
    onSearchQuery(queryString) {
      console.log(queryString);
    },
  },
};
</script>
