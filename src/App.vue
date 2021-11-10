<template>
  <Button text="Planets" />
  <Button text="Galaxies" />
  <Button text="Stars" />
  <Button text="Nebulas" />

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

    <Image image-link="./src/images/Jupiter.jpg" image-text="image" />
    <Image image-link="./images/Triangulum.jpg" image-text="image" />
    <Image image-link="./images/HS-Hydra.jpg" image-text="image" />
    <Image image-link="./images/OrionNebula.jpg" image-text="image" />

  </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Button from '@/components/Button/Button.vue';
import Image from '@/components/Image/Image.vue';

export default defineComponent({
  name: 'App',
  components: {
    Button,
    Image
  },
});
</script>

<style>

</style>
