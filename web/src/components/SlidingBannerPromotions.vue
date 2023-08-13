<template>
  <div class="banner">
    <div class="banner__inner">
      <div class="banner__slider banner__slider--animate">
        <span v-for="offer in offers" :key="offer.id" class="banner__offer">
          {{ offer.text }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SlidingBannerPromotions',
  data() {
    return {
      offers: [
        { id: 1, text: 'Promo! Aprovecha tu primer compra online con descuento 50%' },
      ],
    };
  },
};
</script>

<style scoped>
.banner {
  background-color: var(--arena-dorada);
  height: 40px;
  top: 0;
  position: fixed;
  width: 100vw;
  z-index: 100;
  color: var(--);
  font-family: var(--font-ligth);
}

.banner__inner {
  overflow: hidden;
}

.banner__slider {
  animation: banner__slide 20s linear infinite;
}

.banner__slider--animate {
  animation: banner__slide 20s linear infinite;
}

.banner__offer {
  display: inline-block;
  margin: 10px;
}

@keyframes banner__slide {
  0% {
    transform: translateX(80%);
  }

  100% {
    transform: translateX(-80%);
  }
}
</style>
