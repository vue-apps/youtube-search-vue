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
      e.target.value = e.target.value.replace(/\D/, '');
      this.$emit('searchQuery', e.target.value);
    },
  },
};
</script>

<style></style>
