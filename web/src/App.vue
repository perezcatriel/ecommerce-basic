<template>
  <SlidingBannerPromotions />
</template>

<script>
import SlidingBannerPromotions from './components/SlidingBannerPromotions.vue';

export default {
  name: 'App',
  components: {
    SlidingBannerPromotions,
  },
};
</script >

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}
</style>
