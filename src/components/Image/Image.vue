<template>

  <img class="images" />

</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent ({
  props: {
    imageLink: String,
    imageText: String,
  },
});
</script>

<style scoped>

  .images {
    width: 200px;
    height: 200px;
    padding: 5px;
    margin-top: 20px;
  }

</style>