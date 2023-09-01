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
  name: "SlidingBannerPromotions",
  data() {
    return {
      offers: [
        {
          id: 1,
          text: "Comienza la Primavera!🌻 comienza el calor!🏖️ tenes tú bikini de Mar de Cores?👙",
        },
      ],
    };
  },
};
</script>

<style scoped>
.banner {
  background-color: var(--arena-dorada);
  height: 5vh;
  top: 0;
  position: fixed;
  width: 100vw;
  z-index: 100;
  color: var(--font-dark);
  font-family: var(--font-fine);
}

.banner__inner {
  white-space: nowrap;
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
    transform: translateX(100%);
  }

  100% {
    transform: translateX(-120%);
  }
}

@media (min-width: 768px) {
  .banner {
    height: 55px;
  }
  .banner__offer {
    font-size: 2rem;
  }
  .banner__slider--animate {
    animation: banner__slide 30s linear infinite;
  }
}
</style>
