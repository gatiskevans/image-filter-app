<template>

  <img class="images" src="{{ imageLink }}" alt="{{ imageText }}" />

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

<style>

  .images {
    width: 200px;
    height: 200px;
    padding: 5px;
  }

</style>