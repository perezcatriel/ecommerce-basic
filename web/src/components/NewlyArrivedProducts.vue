<template>
  <h2>Recién llegado</h2>
  <div class="cards">
    <div v-for="(item, index) in items" :key="index">
      <figure>
        <div class="image-container">
          <img :src="item.image" :alt="item.name" class="image">
          <a>
            <img src="@/assets/icons/shop.png" :alt="item.name" class="icon">
          </a>
        </div>

        <h3>{{ item.name }}</h3>
        <p>{{ item.description }}</p>
        <figcaption>{{ item.price }}</figcaption>
      </figure>
    </div>
  </div>
  <button>VER TODO</button>
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
          image: 'https://picsum.photos/id/100/200/300',

        },
        {
          name: 'Producto 2',
          description: 'aqui va la descripcion breve del producto',
          price: 1000000,
          image: 'https://picsum.photos/id/100/200/300',

        },
        {
          name: 'Producto 3',
          description: 'aqui va la descripcion breve del producto',
          price: 1000000,
          image: 'https://picsum.photos/id/100/200/300',

        },
        {
          name: 'Producto 4',
          description: 'aqui va la descripcion breve del producto',
          price: 1000000,
          image: 'https://picsum.photos/id/100/200/300',

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
.cards {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  grid-gap: 10px;
  padding: 10px;
  margin: auto;
  width: 90vw;
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
  width: 40vw;
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
  margin-bottom: 20px;
}
</style>
