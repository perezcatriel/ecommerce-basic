<template>
  <div class="NewCollection">
    <div class="NewCollection-1">
      <div v-for="(item, index) in items_1" :key="index">
        <div class="image">
          <img :src="item.image" alt="item.name" class="image-1" />
          <div>
            <h2>{{ item.name }}</h2>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <div class="combo-image">
      <div class="NewCollection-2">
        <div class="NewCollection-2">
          <div v-for="(item, index) in items_2" :key="index">
            <div class="image">
              <img :src="item.image" alt="item.name" class="image-2" />
              <div>
                <h2>{{ item.name }}</h2>
                <p>{{ item.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="NewCollection-3">
        <div class="NewCollection-3">
          <div v-for="(item, index) in items_3" :key="index">
            <div class="image">
              <img :src="item.image" alt="item.name" class="image-3" />
              <h2 class="image-name">{{ item.name }}</h2>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NewCollections',
  data() {
    return {
      items_1: [
        {
          name: 'Producto 1',
          description: 'descripción del producto',
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
        },
        {
          name: 'Producto 2',
          description: 'descripción del producto',
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
        },
        {
          name: 'Producto 3',
          description: 'descripción del producto',
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
        },
      ],
      items_2: [
        {
          name: 'Producto 4',
          description: 'descripción del producto',
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
        },
      ],
      items_3: [
        {
          name: 'Producto',
          description: 'descripción del producto',
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
        },
        {
          name: 'Producto',
          description: 'descripción del producto',
          image: 'https://i.ibb.co/56KkQx1/magia-cabeza.jpg',
        },
      ],
    };
  },
};
</script>

<style scoped>
.NewCollection {
  max-width: 90vw; /* Limita el ancho al tamaño de la ventana */
  overflow: hidden; /* Evita el desbordamiento horizontal */
  margin: auto;
}

.image {
  margin: -30px auto;
}

.image div {
  position: relative;
  top: -100px;
}

.image-1,
.image-2,
.image-3 {
  max-width: 100%; /* Asegura que las imágenes no se desborden */
  height: auto; /* Mantiene la proporción de la imagen */
}

h2,
p {
  color: var(--blanco-puro);
  text-shadow: 1px 1px var(--font-dark);
}

.NewCollection-2 {
  margin-top: 50px;
}
.combo-image {
  margin: auto;
  padding: 20px;
}
.NewCollection-3 {
  margin: 10px auto;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 150px;
  max-width: 30vw;
}

.image-3 {
  max-width: 45vw;
  margin: 10px auto;
  padding: 0 20px;
}

.image-name {
  font-size: 1.5rem;
  position: relative;
  bottom: 60px;
  z-index: 10;
  padding: 0 10vw;
}

@media (min-width: 768px) {
  .NewCollection-1 {
    margin: 50px auto 0;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 20px;
  }
  .image-1 {
    max-width: 25vw;
  }

  .combo-image {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    width: 60vw;
    height: 90vh;
    margin: auto;
  }

  .image-2 {
    max-width: 40vw;
  }
  .NewCollection-3 {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  .image-3 {
    max-width: 50vw;
    max-height: 30vh;
  }
}

/* ... (resto del código CSS) ... */

@media (min-width: 1024px) {
  .NewCollection {
    width: 100vw;
  }
  .combo-image {
    display: flex;
    justify-items: center; /* Centra los elementos horizontalmente */
    align-items: center; /* Centra los elementos verticalmente */
    width:max-content;
    /* Espacio entre los elementos hijos */
  }
  .image {
    max-width: 100%;
    max-height: 100%;
  }
  .image-2 {
    max-width: 30vw;
    height: auto;
    max-height: 80vh;
  }

  .NewCollection-3 {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 0px;
    overflow: hidden;
    min-width: 50vw;
    margin: auto 20px;
  }

  .image-3 {
    max-width: 30vw;
    height: auto;
    max-height: 70vh;
    object-fit: cover;
  }
}
</style>
