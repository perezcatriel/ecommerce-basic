<template>
  <div class="OurShop">
    <img :src="items.image" :alt="items.name" class="image">
    <h2>{{ items.name }}</h2>
    <p>{{ items.slogan }}</p>
    <button>COMO LLEGAR</button>
  </div>
</template>

<script>
export default {
  name: 'OurShop',
  data() {
    return {
      items: {
        name: 'Mar de Cores | Tienda Física',
        slogan: 'Ropa, Estética y magia para tu alma.',
        image: 'https://picsum.photos/id/100/200/300', // Agrega la ruta correcta de la imagen
      },
    };
  },
};
</script>

<style scoped>
.image {
  width: 90vw;
  margin-bottom: 20px;
}

h2,
p {
  margin-bottom: 10px;
}

button {
  padding: 10px;
  width: 90vw;
  background-color: var(--arena-dorada);
  margin-bottom: 20px;
}
</style>
