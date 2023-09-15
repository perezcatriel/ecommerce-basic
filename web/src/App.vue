<template>
  <SlidingBannerPromotions />
  <NavBar />
  <PresentationCarousel />
  <ProductComponent />
  <NewCollections />
  <ProductComponent
    :items="[
      { name: 'Producto A', description: 'Descripción A', price: 500, image: 'urlA' },
      // ... otros productos ...
    ]"
    title="Productos Más Vendidos"
    iconSrc="@/assets/icons/shop.png"
    buttonLink="#contact-us"
    buttonText="VER TODO"
  />
  <OurShop />
  <CategoryShop />
  <MyJournal />
  <ContactUs />
  <WhatsApp />
</template>

<script>
import SlidingBannerPromotions from './components/SlidingBannerPromotions.vue';
import NavBar from './components/NavBar.vue';
import PresentationCarousel from './components/PresentationCarousel.vue';
import ProductComponent from './components/ProductComponent.vue';
import NewCollections from './components/NewCollections.vue';
import OurShop from './components/OurShop.vue';
import CategoryShop from './components/CategoryShop.vue';
import ContactUs from './components/ContactUs.vue';
import MyJournal from './components/MyJournal.vue';
import WhatsApp from './components/WhatsApp.vue';

export default {
  name: 'App',
  components: {
    SlidingBannerPromotions,
    NavBar,
    PresentationCarousel,
    ProductComponent,
    NewCollections,
    OurShop,
    CategoryShop,
    MyJournal,
    ContactUs,
    WhatsApp,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-shadow: none;
}

html {
  scroll-behavior: smooth;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--font-dark);
  margin-top: 60px;
}
</style>
