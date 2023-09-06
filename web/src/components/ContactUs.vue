<template>
  <footer class="footer" id="contact-us">
    <div class="social-container">
      <div v-for="(item, index) in social" :key="index" class="social">
        <a :href="item.link" target="_blank">
          <img :src="item.image" :alt="item.name" class="social-link">
          <span class="social-name">{{ item.name }}</span>
        </a>
      </div>
    </div>

    <div class="cards-container">
      <div v-for="(item, index) in cards" :key="index" class="cards">
        <img :src="item.image" :alt="item.name" class="cards-link">
      </div>
    </div>

    <div class="rights">
      <p>&copy; {{ currentYear }} Todos los derechos reservados.</p>
      <p>Creado por <a href="https://datacraft.vercel.app/" target="_blank">DataCraft</a></p>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
      social: [
        {
          name: '@marde_cores',
          image: '../assets/icons/instagram.png',
          link: 'https://www.instagram.com/marde_cores/',
        },
        {
          name: '@marde_cores.estetica',
          image: '../assets/icons/instagram.png',
          link: 'https://www.instagram.com/marde_cores.estetica/',
        },
        {
          name: 'mardecorestienda@gmail.com',
          image: '../assets/icons/gmail.png',
          link: 'mailto:mardecorestienda@gmail.com',
        },
      ],
      cards: [
        {
          name: 'master card',
          image: '../assets/icons/master card.png',
        },
        {
          name: 'visa',
          image: '../assets/icons/visa.png',
        },
        {
          name: 'mercado pago',
          image: '../assets/icons/atm-card.png',
        },
      ],
    };
  },
};
</script>

<style scoped>
.footer {
  background-color: var(--font-dark);
  color: var(--background-color);
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  height: 50vh;
}

.social-container {
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 10px;
}

.social a {
  display: flex;
  align-items: center;
  text-decoration: none;
}

.social-link,
.cards-link {
  width: 20px;
  height: 20px;
  color: var(--background-color);
}

.social-name {
  color: var(--arena-dorada);
  padding-left: 10px;
}

.cards-container {
  display: flex;
  flex-direction: row;
  align-items: space-around;
}

.cards {
  padding: 0 20px;
}

.rights {
  margin-top: 10px;
}

.rights a {
  color: var(--arena-dorada);
  text-decoration: none;
}
</style>
