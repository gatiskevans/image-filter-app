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
      display: inline-block;
      border: 1px solid black;
      border-radius: 3px;
      padding: 10px 62px;
    }

</style>