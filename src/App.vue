<template>

  <div class="imageList">

    <h1>Filter App</h1>

    <div class="navigation">
      <Nav :text="all()" @click="showAllImages"/>
      <Nav :text="planetsLink()" @click="showPlanets"/>
      <Nav :text="galaxiesLink()" @click="showGalaxies"/>
      <Nav :text="starsLink()" @click="showStars"/>
      <Nav :text="nebulasLink()" @click="showNebulas"/>
    </div>

   <div v-if="!planetsHidden" class="imageContainer">
     <div v-for="image in planets" :key="image" class="contents">
       <Image :src="image.link" :alt="getAlt()" />
       <span>{{ image.name }}</span>
     </div>
   </div>

    <div v-if="!galaxiesHidden" class="imageContainer">
      <div v-for="image in galaxies" :key="image" class="contents">
        <Image :src="image.link" :alt="getAlt()" />
        <span>{{ image.name }}</span>
      </div>
    </div>

    <div v-if="!starsHidden" class="imageContainer">
      <div v-for="image in stars" :key="image" class="contents">
        <Image :src="image.link" :alt="getAlt()" />
        <span>{{ image.name }}</span>
      </div>
    </div>

    <div v-if="!nebulasHidden" class="imageContainer">
      <div v-for="image in nebulas" :key="image" class="contents">
        <Image :src="image.link" :alt="getAlt()" />
        <span>{{ image.name }}</span>
      </div>
    </div>

  </div>

</template>

<script lang="ts">
import {defineComponent} from 'vue';
import Nav from '@/components/Navigation/Nav.vue';
import Image from '@/components/Image/Image.vue';

export default defineComponent({
  name: 'App',
  components: {
    Nav,
    Image,
  },
  data: () => ({
    navItems: ['All', 'Planets', 'Galaxies', 'Stars', 'Nebulas'],

    planets: [
      {
        id: 1,
        name: 'Earth',
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/The_Earth_seen_from_Apollo_17.jpg/240px-The_Earth_seen_from_Apollo_17.jpg",
      },
      {
        id: 2,
        name: 'Jupiter',
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Jupiter_and_its_shrunken_Great_Red_Spot.jpg/240px-Jupiter_and_its_shrunken_Great_Red_Spot.jpg",
      }
    ],

    galaxies: [
      {
        id: 1,
        name: "Andromeda",
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Andromeda_Galaxy_560mm_FL.jpg/320px-Andromeda_Galaxy_560mm_FL.jpg",
      },
      {
        id: 2,
        name: "Triangulum",
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/VST_snaps_a_very_detailed_view_of_the_Triangulum_Galaxy.jpg/402px-VST_snaps_a_very_detailed_view_of_the_Triangulum_Galaxy.jpg"
      }
    ],

    stars: [
      {
        id: 1,
        name: "Pleiades Star Cluster",
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Pleiades_large.jpg/320px-Pleiades_large.jpg",
      },
      {
        id: 2,
        name: "Betelgeuse",
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/57/Betelgeuse_captured_by_ALMA.jpg/480px-Betelgeuse_captured_by_ALMA.jpg"
      }
    ],

    nebulas: [
      {
        id: 1,
        name: "Eagle Nebula",
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Eagle_Nebula_from_ESO.jpg/480px-Eagle_Nebula_from_ESO.jpg",
      },
      {
        id: 2,
        name: "Orion Nebula",
        link: "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Orion_Nebula_-_Hubble_2006_mosaic_18000.jpg/240px-Orion_Nebula_-_Hubble_2006_mosaic_18000.jpg"
      }
    ],

    alt: "image",

    planetsHidden: false,
    galaxiesHidden: false,
    starsHidden: false,
    nebulasHidden: false,

  }),

  methods: {

    showAllImages() {
      this.planetsHidden = this.galaxiesHidden = this.starsHidden = this.nebulasHidden = false;
    },

    showPlanets() {
      this.planetsHidden = false;
      this.galaxiesHidden = this.starsHidden = this.nebulasHidden = true;
    },

    showGalaxies() {
      this.galaxiesHidden = false;
      this.planetsHidden = this.starsHidden = this.nebulasHidden = true;
    },

    showStars() {
      this.starsHidden = false;
      this.planetsHidden = this.galaxiesHidden = this.nebulasHidden = true;
    },

    showNebulas() {
      this.nebulasHidden = false;
      this.planetsHidden = this.galaxiesHidden = this.starsHidden = true;
    },

    linkNames(item: number) {
      return this.navItems[item];
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

    getAlt() {
      return this.alt;
    }
  }
});
</script>

<style>

.imageList {
  text-align: center;
  margin: auto;
  width: 1400px;
  padding: 5px;
}

.imageContainer {
  border-radius: 3px;
  display: inline-block;
  border: 1px solid black;
  margin: 0 5px 10px 5px;
  padding-bottom: 10px;
}

.contents {
  display: inline-block;
  width: 40%;
}

.navigation {
  margin-bottom: 10px;
}

</style>
