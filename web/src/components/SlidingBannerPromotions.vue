<template>
  <div class="banner">
    <div class="overflow-hidden h-full">
      <div class="animate-slide whitespace-nowrap">
        <span v-for="offer in offers" :key="offer.id" class="inline-block mx-10">
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
  background-color: var(--rosa-encantado);
  height: 40px;
  top: 0;
  position: fixed;
  width: 100vw;
  z-index: 100;
  color: var(--font-dark);
  font-family: var(--font-fine);
}

.overflow-hidden {
  overflow: hidden;
}

.whitespace-nowrap {
  white-space: nowrap;
}

@keyframes slide {
  0% {
    transform: translateX(80%);
  }

  100% {
    transform: translateX(-80%);
  }
}

.animate-slide {
  animation: slide 20s linear infinite;
}
</style>
