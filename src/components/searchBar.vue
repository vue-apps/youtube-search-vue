<template>
  <div class="input-group input-group-sm my-3">
    <div class="input-group-prepend">
      <span class="input-group-text" id="inputGroup-sizing-default"
        >Search youtube video</span
      >
    </div>
    <input
      @input="onInput"
      type="text"
      class="form-control"
      aria-label="Small"
      aria-describedby="inputGroup-sizing-default"
    />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {
    onInput(e) {
      this.$emit('searchQuery', e.target.value);
    },
  },
};
</script>
