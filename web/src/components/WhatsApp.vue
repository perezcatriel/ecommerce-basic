<template>
  <div class="whatsapp-container">
    <a href="https://wa.me/543541204400">
      <img src="../assets/icons/whatsapp.png" alt="WhatsApp">
      <div v-if="showNotification" class="notification">1</div>
    </a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'WhatsApp',
      showNotification: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showNotification = true;
    }, 5000);
  },
};
</script>

<style scoped>
.whatsapp-container {
  position: relative;
}

img {
  width: 40px;
  height: 40px;
  position: fixed;
  bottom: 20px;
  right: 20px;
}

.notification {
  position: fixed;
  top: calc(100vh - 85px);
  right: 15px;
  background-color: var(--arena-dorada);
  color: var(--font-dark);
  border-radius: 50%;
  box-shadow: 0px 0px 5px var(--font-dark);
  width: 20px;
  height: 20px;
  text-align: center;
  line-height: 20px;
  font-size: 12px;
  animation: fadeIn 1s;
  z-index: 20;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
