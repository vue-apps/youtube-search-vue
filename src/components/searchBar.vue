<template>
  <div>
    <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: 'searchBar',
  methods: {
    onInput(e) {
      this.$emit('searchQuery', e.target.value);
    },
  },
};
</script>

<style></style>
