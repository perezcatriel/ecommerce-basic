<template>
  <SlidingBannerPromotions />
  <NavBar />
  <PresentationCarousel />
  <NewlyArrivedProducts />
  <NewCollections />
</template>

<script>
import SlidingBannerPromotions from './components/SlidingBannerPromotions.vue';
import NavBar from './components/NavBar.vue';
import PresentationCarousel from './components/PresentationCarousel.vue';
import NewlyArrivedProducts from './components/NewlyArrivedProducts.vue';
import NewCollections from './components/NewCollections.vue';

export default {
  name: 'App',
  components: {
    SlidingBannerPromotions,
    NavBar,
    PresentationCarousel,
    NewlyArrivedProducts,
    NewCollections,
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
