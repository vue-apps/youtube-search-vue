<template>
  <div>
    <SearchBar @searchQuery="onSearchQuery" />
  </div>
</template>

<script>
import SearchBar from './components/searchBar';

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
