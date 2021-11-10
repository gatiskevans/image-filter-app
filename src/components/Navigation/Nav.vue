<template>

  <a href="#" v-for="item in navItems" :key="item" class="nav">
    {{ item }}
  </a>
    
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent ({
    props: {
        text: String,
    },
  data: () => ({
    navItems: ['All', 'Planets', 'Galaxies', 'Stars', 'Nebulas'],
  }),
});
</script>

<style>

    .nav {
      border: 1px solid black;
      padding: 10px 62px;
      display: inline;
    }

</style>