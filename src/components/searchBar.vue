<template>
  <div>
    <label for="search" class="d-block">Enter only a number: </label>
    <input @input="onInput" id="search" />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {
    onInput(e) {
      // e.target.value = e.target.value.replace(/\D/, '');
      this.$emit('searchQuery', e.target.value);
    },
  },
};
</script>

<style scoped>
input {
  width: 75%;
}

div {
  text-align: center;
}
</style>
