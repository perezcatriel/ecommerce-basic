<template>
  <div class="carousel-container">
    <div class="card">
      <img :src="items[currentIndex].image" alt="Imagen de la tarjeta" class="card-image" />
      <h3 class="card-title">{{ items[currentIndex].name }}</h3>
      <p class="card-description">{{ items[currentIndex].description }}</p>
    </div>

    <div>
      <button @click="prevCard">Anterior</button>
      <button @click="nextCard">Siguiente</button>
    </div>

    <div>
      <img src="" alt="">
      <img src="" alt="">
      <img src="" alt="">
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
          image: '../assets/images/image-example.webp',
          name: 'Nombre 2',
          description: 'Descripción 2',
        },
        {
          id: 3,
          image: '../assets/images/image-example.webp',
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
      if (this.currentIndex < this.items.length - 1) {
        // eslint-disable-next-line no-plusplus
        this.currentIndex++;
      } else {
        this.currentIndex = 0;
      }
    },
    prevCard() {
      if (this.currentIndex > 0) {
        // eslint-disable-next-line no-plusplus
        this.currentIndex--;
      } else {
        this.currentIndex = this.items.length - 1;
      }
    },
    startAutoSlide() {
      this.autoSlideInterval = setInterval(this.nextCard, 3000); // Cambia cada 3 segundos
    },
    stopAutoSlide() {
      clearInterval(this.autoSlideInterval);
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

button {
  position: relative;
  top: -130px;
  background-color: #fff;
  border: 1px solid #ccc;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #f0f0f0;
}

button:disabled {
  background-color: #eee;
  cursor: not-allowed;
}

button:nth-of-type(1) {
  left: -60px;
}

button:nth-of-type(2) {
  right: -60px;
}
</style>
