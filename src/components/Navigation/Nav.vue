<template>

  <button type="submit" class="nav" @submit.prevent="" >
    {{ text }}
  </button>
    
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent ({
    props: {
        text: String,
    },
});
</script>

<style>

    .nav {
      border: 1px solid black;
      padding: 10px 62px;
      display: inline;
    }

</style>