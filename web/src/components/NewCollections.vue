<template>
  <div class="NewCollection">
    <div class="NewCollection-1">
      <div v-for="(item, index) in items_1" :key="index">
        <div class="image">
          <img :src="item.image" alt="item.name" class="image-1">
          <div>
            <h2>{{ item.name }}</h2>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <div class="NewCollection-2">
      <div class="NewCollection-2">
        <div v-for="(item, index) in items_2" :key="index">
          <div class="image">
            <img :src="item.image" alt="item.name" class="image-1">
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
            <img :src="item.image" alt="item.name" class="image-3">
            <h2 class="image-name">{{ item.name }}</h2>
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
          image: 'https://picsum.photos/id/100/200/300',
        },
        {
          name: 'Producto 2',
          description: 'descripción del producto',
          image: 'https://picsum.photos/id/100/200/300',
        },
        {
          name: 'Producto 3',
          description: 'descripción del producto',
          image: 'https://picsum.photos/id/100/200/300',
        },
      ],
      items_2: [
        {
          name: 'Producto 4',
          description: 'descripción del producto',
          image: 'https://picsum.photos/id/100/200/300',
        },
      ],
      items_3: [
        {
          name: 'Producto',
          description: 'descripción del producto',
          image: 'https://picsum.photos/id/100/200/300',
        },
        {
          name: 'Producto',
          description: 'descripción del producto',
          image: 'https://picsum.photos/id/100/200/300',
        },
      ],
    };
  },
};
</script>

<style scoped>
.NewCollection-1 {
  margin: 0;
  padding: 0;
}

.image {
  margin: 10px 0 -30px;
  padding: 0;
  height: 550px;
}

.image div {
  margin: 0;
  position: relative;
  top: -100px;
}

.image-1 {
  width: 90vw;
  margin: 0;
}

h2,
p {
  color: var(--blanco-puro);
  text-shadow: 1px 1px var(--font-dark);
}

.NewCollection-2 {
  margin-top: 50px;
}

.NewCollection-3 {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 46vw;
  padding: 0 10px;
  height: 300px;
}

.image-3 {
  width: 44vw;
}

.image-name {
  font-size: 1.5rem;
  position: relative;
  bottom: 60px;
  z-index: 10;
  padding: 0 25px;
}
</style>
