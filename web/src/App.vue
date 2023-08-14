<template>
  <SlidingBannerPromotions />
  <NavBar />
  <PresentationCarousel />
</template>

<script>
import SlidingBannerPromotions from './components/SlidingBannerPromotions.vue';
import NavBar from './components/NavBar.vue';
import PresentationCarousel from './components/PresentationCarousel.vue';

export default {
  name: 'App',
  components: {
    SlidingBannerPromotions,
    NavBar,
    PresentationCarousel,
  },
};
</script >

<style>
* {
  margin: 0;
  padding: 0;
  box-shadow: none;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--font-dark);
  margin-top: 60px;
}
</style>
