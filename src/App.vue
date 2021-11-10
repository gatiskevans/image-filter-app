<template>

  <Nav />

  <div>
    <img
        src="./images/Earth.jpg"
        alt="image"
        class="images" />
    <img
        src="./images/Andromeda.jpg"
        alt="image"
        class="images" />
    <img
        src="./images/Pleiades.jpg"
        alt="image"
        class="images" />
    <img
        src="./images/Eagle.jpg"
        alt="image"
        class="images" />
  </div>
  <div>

    <img
        src="./images/Jupiter.jpg"
        alt="image"
        class="images" />
    <img
        src="./images/Triangulum.jpg"
        alt="image"
        class="images" />
    <img
        src="./images/HS-Hydra.jpg"
        alt="image"
        class="images" />
    <img
        src="./images/OrionNebula.jpg"
        alt="image"
        class="images" />
  </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Nav from '@/components/Navigation/Nav.vue';

export default defineComponent({
  name: 'App',
  components: {
    Nav,
  },
  data: () => ({
    planets: ['Earth', 'Jupiter'],
    galaxies: ['Andromeda', 'Triangulum'],
    stars: ['Pleiades', 'Hydra'],
    nebulas: ['Eagle', 'Orion'],
  })
});
</script>

<style>

  .images {
    width: 200px;
    height: 200px;
    padding: 5px;
    margin-top: 20px;
  }

</style>
