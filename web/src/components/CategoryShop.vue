<template>
  <div class="CategoryShop">
    <h2>Categorias</h2>
    <div class="cards">
      <div class="image uno">
        <img :src="items_1[0].image" :alt="items_1[0].name">
        <p>{{ items_1[0].name }}</p>
      </div>
      <div class="image dos">
        <img :src="items_1[1].image" :alt="items_1[1].name">
        <p>{{ items_1[1].name }}</p>
      </div>
      <div class="image tres">
        <img :src="items_2.image" :alt="items_2.name">
        <p>{{ items_2.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CategoryShop',
  data() {
    return {
      items_1: [
        {
          name: 'Estética',
          image: 'https://picsum.photos/id/100/200/300',
        },
        {
          name: 'Magia',
          image: 'https://picsum.photos/id/100/200/300',
        },
      ],
      items_2: {
        name: 'Ropa',
        image: 'https://picsum.photos/id/100/400/300', // Cambié el ancho de la imagen para que cubra el ancho completo
      },
    };
  },
};
</script>

<style scoped>
.CategoryShop {
  width: 90vw;
  margin: auto;
}

.cards {
  display: grid;
  grid-template-areas:
    "uno dos"
    "tres tres";
  grid-gap: 5px;
  align-items: center;
  text-align: center;
}

.image {
  display: flex;
  flex-direction: column;
}

.image p {
  position: relative;
  bottom: 50px;
  color: var(--blanco-puro);
  text-shadow: 1px 1px var(--font-dark);
  font-size: 1.5rem;
  font-weight: bold;
}

.uno {
  grid-area: uno;
  width: 44vw;
}

.dos {
  grid-area: dos;
  width: 44vw;
}

.tres {
  grid-area: tres;
  width: 90vw;
  margin-top: -15px;
}
</style>
