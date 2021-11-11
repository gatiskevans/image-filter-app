<template>

  <h1>Filter App</h1>

  <Nav :text="all()" @click="showAllImages" />
  <Nav :text="planetsLink()" @click="showPlanets" />
  <Nav :text="galaxiesLink()" @click="showGalaxies" />
  <Nav :text="starsLink()" @click="showStars" />
  <Nav :text="nebulasLink()" @click="showNebulas" />

  <div class="imageList">

    <div v-if="!planetsHidden" class="imageContainer" >
      <Image v-for="image in planetsLinks" :key="image" :src="image" alt="alt"/>
      <br/>
      <div class="imageName" v-for="name in planets" :key="name" >{{ name }}</div>
    </div>

    <div v-if="!galaxiesHidden" class="imageContainer">
      <Image v-for="image in galaxiesLinks" :key="image" :src="image" alt="alt"/>
      <br/>
      <div class="imageName" v-for="name in galaxies" :key="name" >{{ name }}</div>
    </div>

    <div v-if="!starsHidden" class="imageContainer">
      <Image v-for="image in starsLinks" :key="image" :src="image" alt="alt"/>
      <br/>
      <div class="imageName" v-for="name in stars" :key="name" >{{ name }}</div>
    </div>

    <div v-if="!nebulasHidden" class="imageContainer">
      <Image v-for="image in nebulasLinks" :key="image" :src="image" alt="alt"/>
      <br/>
      <div class="imageName" v-for="name in nebulas" :key="name" >{{ name }}</div>
    </div>

  </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Nav from '@/components/Navigation/Nav.vue';
import Image from '@/components/Image/Image.vue';

export default defineComponent({
  name: 'App',
  components: {
    Nav,
    Image,
  },
  methods: {
    showAllImages() {
      this.planetsHidden = false;
      this.galaxiesHidden = false;
      this.starsHidden = false;
      this.nebulasHidden = false;
    },
    showPlanets() {
      this.planetsHidden = false;
      this.galaxiesHidden = true;
      this.starsHidden = true;
      this.nebulasHidden = true;
    },
    showGalaxies() {
      this.planetsHidden = true;
      this.galaxiesHidden = false;
      this.starsHidden = true;
      this.nebulasHidden = true;
    },
    showStars() {
      this.planetsHidden = true;
      this.galaxiesHidden = true;
      this.starsHidden = false;
      this.nebulasHidden = true;
    },
    showNebulas() {
      this.planetsHidden = true;
      this.galaxiesHidden = true;
      this.starsHidden = true;
      this.nebulasHidden = false;
    },
    all() {
      return this.navItems[0];
    },
    planetsLink() {
      return this.navItems[1];
    },
    galaxiesLink() {
      return this.navItems[2];
    },
    starsLink() {
      return this.navItems[3];
    },
    nebulasLink() {
      return this.navItems[4];
    },
  },
  data: () => ({
    navItems: ['All', 'Planets', 'Galaxies', 'Stars', 'Nebulas'],
    alt: "image",
    planets: ['Earth', 'Jupiter'],
    planetsHidden: false,
    galaxies: ['Andromeda', 'Triangulum'],
    galaxiesHidden: false,
    stars: ['Pleiades', 'Betelgeuse'],
    starsHidden: false,
    nebulas: ['Eagle', 'Orion'],
    nebulasHidden: false,
    planetsLinks: [
        "https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/The_Earth_seen_from_Apollo_17.jpg/240px-The_Earth_seen_from_Apollo_17.jpg",
        "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Jupiter_and_its_shrunken_Great_Red_Spot.jpg/240px-Jupiter_and_its_shrunken_Great_Red_Spot.jpg"
    ],
    galaxiesLinks: [
        "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Andromeda_Galaxy_560mm_FL.jpg/320px-Andromeda_Galaxy_560mm_FL.jpg",
        "https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/VST_snaps_a_very_detailed_view_of_the_Triangulum_Galaxy.jpg/402px-VST_snaps_a_very_detailed_view_of_the_Triangulum_Galaxy.jpg"
    ],
    starsLinks: [
      "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Pleiades_large.jpg/320px-Pleiades_large.jpg",
      "https://upload.wikimedia.org/wikipedia/commons/thumb/5/57/Betelgeuse_captured_by_ALMA.jpg/480px-Betelgeuse_captured_by_ALMA.jpg"
    ],
    nebulasLinks: [
        "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Eagle_Nebula_from_ESO.jpg/480px-Eagle_Nebula_from_ESO.jpg",
        "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Orion_Nebula_-_Hubble_2006_mosaic_18000.jpg/240px-Orion_Nebula_-_Hubble_2006_mosaic_18000.jpg"
    ]
  })
});
</script>

<style>

  .imageList {
    width: 470px;
  }

  .imageContainer {
    padding: 20px;
    border: 1px solid black;
  }

  .imageName {
    width: auto;
    display: inline;
    padding: 70px;
  }

</style>
