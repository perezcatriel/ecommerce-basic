<template>
  <div class="navbar">
    <img src="../assets/icons/menu.svg" alt="">
    <h1>Mar de Cores</h1>
    <img src="../assets/icons/search.svg" alt="">
    <img src="../assets/icons/user.png" alt="">
  </div>
</template>

<script>
export default {
  name: 'NavBar',
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-around;
}

h1 {
  font-family: var(--font-cursive);
}
</style>
