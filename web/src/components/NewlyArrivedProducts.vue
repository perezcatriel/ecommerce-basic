<template>
  <div class="center-container">
    <h2>Recién llegado</h2>

    <div class="cards-container">
      <div class="card-row">
        <div v-for="(item, index) in items.slice(0, 2)" :key="index" class="card">
          <figure>
            <div class="image-container">
              <img :src="item.image" :alt="item.name" class="image" />
              <a>
                <img src="@/assets/icons/shop.png" :alt="item.name" class="icon" />
              </a>
            </div>

            <h3>{{ item.name }}</h3>
            <p>{{ item.description }}</p>
            <figcaption>{{ item.price }}</figcaption>
          </figure>
        </div>
      </div>
      <div class="card-row">
        <div v-for="(item, index) in items.slice(2, 4)" :key="index" class="card">
          <figure>
            <div class="image-container">
              <img :src="item.image" :alt="item.name" class="image" />
              <a>
                <img src="@/assets/icons/shop.png" :alt="item.name" class="icon" />
              </a>
            </div>

            <h3>{{ item.name }}</h3>
            <p>{{ item.description }}</p>
            <figcaption>{{ item.price }}</figcaption>
          </figure>
        </div>
      </div>
    </div>

    <a href="#contact-us"><button>VER TODO</button></a>
  </div>
</template>

<script>
// import GenericButton from '@/components/GenericButton.vue';

export default {
  name: 'NewlyArrivedProducts',
  data() {
    return {
      items: [
        {
          name: 'Producto 1',
          description: 'aqui va la descripcion breve del producto',
          price: 1000000,
          image: 'https://i.ibb.co/447b8SH/ropa-pinza.jpg',
        },
        {
          name: 'Producto 2',
          description: 'aqui va la descripcion breve del producto',
          price: 1000000,
          image: 'https://i.ibb.co/PmcD3zH/ropa-arito-estrellas.jpg',
        },
        {
          name: 'Producto 3',
          description: 'aqui va la descripcion breve del producto',
          price: 1000000,
          image: 'https://i.ibb.co/T2s6jjS/ropa-brazalete.jpg',
        },
        {
          name: 'Producto 4',
          description: 'aqui va la descripcion breve del producto',
          price: 1000000,
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
        },
      ],
    };
  },
  components: {
    // GenericButton,
  },
  methods: {
    handleClick() {
      // Lógica a ejecutar cuando se hace clic en el botón
    },
  },
};
</script>

<style scoped>
.center-container {
  text-align: center;
  padding: 20px;
}

.cards-container {
  display: flex;
  flex-direction: column;
  align-items: center; /* Centra horizontalmente */
  margin-top: 20px;
}

.card-row {
  display: flex;
  justify-content: center; /* Centra horizontalmente */
  margin-bottom: 20px;
}

.card {
  margin: 0 10px; /* Espacio entre las tarjetas */
  text-align: start;
}

figure {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: start;
}

.image-container {
  position: relative;
  width: auto;
}

img.image {
  width: 100%; /* Ajusta el ancho de la imagen */
  max-width: 300px; /* Limita el ancho máximo de la imagen */
}

img.icon {
  position: absolute;
  bottom: 10px;
  right: 10px;
  width: 24px;
  height: 24px;
}

button {
  padding: 10px;
  width: 90vw;
  background-color: var(--arena-dorada);
  margin: 20px auto; /* Centra horizontalmente */
}

@media (min-width: 768px) {
  img.image {
    max-width: 600px;
  }
}
</style>
