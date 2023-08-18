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
      <div class="icons">
        <img v-for="(icon, iconIndex) in icons" :key="iconIndex" :src="icon.image" :alt="icon.name"
          :style="{ opacity: activeIcon === iconIndex ? 1 : 0.2 }" @click="goToSlide(iconIndex)"
          @keydown.enter="goToSlide(index)" tabindex="0" />
      </div>
      <button>VER TODO</button>
    </div>

  </div>
</template>

<script>
export default {
  name: 'PresentationCarousel',
  data() {
    return {
      currentIndex: 0,
      activeIcon: 0,
      autoSlideInterval: null,
      items: [
        {
          id: 1,
          // eslint-disable-next-line global-require
          image: 'https://i.ibb.co/Sm18g3t/ropa-bota.jpg',
          name: 'Bota goma Ecológica',
          description: 'Estilo, comodidad bajo la lluvia',
          category: 'Ropa',
        },
        {
          id: 2,
          image: 'https://i.ibb.co/zbgP4xx/estetica-servicios.jpg',
          name: 'Servicios de Estética',
          description: 'Cuidate y mimate en Mar de Cores',
          category: 'Estética',
        },
        {
          id: 3,
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
          name: 'Buda Cabeza',
          description: 'Sabiduria, tranquilidad y paciencia',
          category: 'Magia',
        },
      ],
      icons: [
        {
          name: 'Ropa',
          image: 'https://i.ibb.co/F41JH1d/marde-caracol-azul.jpg',
        },
        {
          name: 'Estética',
          image: 'https://i.ibb.co/jzryk0c/marde-caracol-rosa.jpg',
        },
        {
          name: 'Magia',
          image: 'https://i.ibb.co/MRsBynT/mardecores-caracol-naranja.jpg',
        },
      ],
      categoryToIcon: {
        Ropa: 0, // Índice del ícono de 'Ropa' en la matriz 'icons'
        Estética: 1, // Índice del ícono de 'Estética' en la matriz 'icons'
        Magia: 2, // Índice del ícono de 'Magia' en la matriz 'icons'
        // Agrega más categorías e índices según sea necesario
      },
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
      this.autoSlideInterval = setInterval(() => {
        this.nextCard();
        const currentCategory = this.items[this.currentIndex].category;
        this.activeIcon = this.categoryToIcon[currentCategory];
      }, 3000);
    },
    stopAutoSlide() {
      clearInterval(this.autoSlideInterval);
    },
    goToSlide(index) {
      this.currentIndex = index;
      const currentCategory = this.items[index].category;
      this.activeIcon = this.categoryToIcon[currentCategory];
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
  object-fit: scale-down;
}

.card-title,
.card-description {
  margin: 10px;
}

button {
  padding: 10px;
  width: 90vw;
  background-color: var(--arena-dorada);
  margin-bottom: 20px;
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
  margin-bottom: 20px;
}

.icons img {
  margin: 10px;
  width: 40px;
  height: 40px;
  border-radius: 50%;
}
</style>
