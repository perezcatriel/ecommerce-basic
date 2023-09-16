<template>
    <div class="carousel">
        <h2>Mi Blog</h2>
        <div class="carousel-container">
            <div class="carousel-track" :style="trackStyles">
                <div class="carousel-slide" v-for="(item, index) in items" :key="index">
                    <div class="slide-content">
                        <div class="image-container">
                            <img :src="item.image" :alt="item.name" class="image">
                        </div>
                        <h3>{{ item.name }}</h3>
                        <p>{{ item.date }}</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="carousel-controls">
            <button class="carousel-prev" @click="prevSlide">Anterior</button>
            <button class="carousel-next" @click="nextSlide">Siguiente</button>
        </div>
    </div>
</template>

<script>
export default {
  name: 'MyJournal',
  data() {
    return {
      currentIndex: 0,
      items: [
        {
          image: 'https://picsum.photos/id/100/200/300',
          name: 'My Journal 1',
          date: '2020-01-01',
        },
        {
          image: 'https://picsum.photos/id/101/200/300',
          name: 'My Journal 2',
          date: '2020-01-02',
        },
        {
          image: 'https://picsum.photos/id/102/200/300',
          name: 'My Journal 3',
          date: '2020-01-03',
        },
      ],
    };
  },
  computed: {
    trackStyles() {
      return {
        transform: `translateX(-${this.currentIndex * 100}%)`,
      };
    },
  },
  methods: {
    prevSlide() {
      this.currentIndex = Math.max(this.currentIndex - 1, 0);
    },
    nextSlide() {
      this.currentIndex = Math.min(
        this.currentIndex + 1,
        this.items.length - 1,
      );
    },
  },
};
</script>

<style scoped>
.carousel {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    overflow: hidden;
}

.carousel-container {
    width: 100%;
    display: flex;
    overflow: hidden;
}

.carousel-track {
    display: flex;
    transition: transform 0.3s ease-in-out;
    white-space: nowrap;
}

.carousel-slide {
    flex: 0 0 100%;
    text-align: center;
    display: flex;
    justify-content: center;
}

.slide-content {
    text-align: center;
}

.carousel img {
    max-width: 100%;
}

.carousel-controls {
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 20px;
    width: 100%;
}

.carousel-prev,
.carousel-next {
    padding: 10px;
    cursor: pointer;
    background-color: var(--arena-dorada);
    border: none;
    border-radius: 4px;
    font-size: 14px;
}

.carousel-prev {
    left: 10px;
}

.carousel-next {
    right: 10px;
}

@media (min-width: 768px) {
  .carousel-container {
      width: 50%; /* Ajusta el ancho según tus necesidades */
      margin: 0 auto;
  }

  .carousel-slide {
      padding: 0 20px; /* Añade un poco de espaciado a los lados de cada slide */
  }

  .carousel img {
      width: 80vw; /* Ajusta el tamaño de la imagen */
      max-height: 70vh;
      margin: 0 auto;
      object-fit: contain;
  }

  .carousel-controls {
      justify-content: space-evenly; /* Centra los botones de control */
  }
}
</style>
