<template>
  <div class="carousel-container">
    <div class="card">
      <img :src="items[currentIndex].image" alt="Imagen de la tarjeta" class="card-image" />
      <div class="slider-container">
        <div v-for="(item, index) in items" :key="item.id" :class="['slider',
          { active: index === currentIndex }
        ]" @click="goToSlide(index)" @keydown.enter="goToSlide(index)" tabindex="0">
        </div>
      </div>
      <h3 class="card-title">{{ items[currentIndex].name }}</h3>
      <p class="card-description">{{ items[currentIndex].description }}</p>
    </div>
    <div class="icons">
      <img src="../assets/icons/shop.png" alt="icon 1">
      <img src="../assets/icons/shop.png" alt="icon 2">
      <img src="../assets/icons/shop.png" alt="icon 3">
    </div>
  </div>
</template>

<script>
export default {
  name: 'PresentationCarousel',
  data() {
    return {
      currentIndex: 0,
      autoSlideInterval: null,
      items: [
        {
          id: 1,
          // eslint-disable-next-line global-require
          image: '../assets/images/image-example.webp',
          name: 'Nombre 1',
          description: 'Descripción 1',
        },
        {
          id: 2,
          image: '../assets/images/image-example-2.webp',
          name: 'Nombre 2',
          description: 'Descripción 2',
        },
        {
          id: 3,
          image: '../assets/images/image-example-3.webp',
          name: 'Nombre 3',
          description: 'Descripción 3',
        },
      ],
    };
  },
  created() {
    this.startAutoSlide();
  },
  beforeUnmount() {
    this.stopAutoSlide();
  },
  methods: {
    nextCard() {
      this.currentIndex = (this.currentIndex + 1) % this.items.length;
    },
    prevCard() {
      this.currentIndex = (this.currentIndex - 1 + this.items.length) % this.items.length;
    },
    startAutoSlide() {
      this.autoSlideInterval = setInterval(this.nextCard, 3000); // Cambia cada 3 segundos
    },
    stopAutoSlide() {
      clearInterval(this.autoSlideInterval);
    },
    goToSlide(index) {
      this.currentIndex = index;
    },
  },
};
</script>

<style scoped>
.carousel-container {
  width: 100vw;
  margin: auto;
}

.card {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  overflow: hidden;
}

.card-image {
  width: 100vw;
  height: 40vh;
  object-fit: cover;
}

.card-title,
.card-description {
  margin: 10px;
}

.slider-container {

  display: flex;
  justify-content: center;
  margin-top: 20px;
  z-index: 50;
}

.slider {
  width: 50px;
  height: 10px;
  background-color: var(--font-ligth);
  margin: 0 5px;
  cursor: pointer;
}

.slider.active {
  background-color: var(--font-dark);
}

.icons {
  background-color: var(--background-color);
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.icons img {
  margin: 10px;
}
</style>
