<template>
  <div class="navbar">
    <div class="navbar__icon">
      <img src="../assets/icons/menu.svg" alt="menu icon" class="navbar__menu">
    </div>
    <h1>Mar de Cores</h1>
    <div class="navbar__icon">
      <img src="../assets/icons/search.svg" alt="search icon" class="navbar__search">
      <img src="../assets/icons/user.png" alt="user icon" class="navbar__user">
    </div>

  </div>
</template>

<script>
export default {
  name: 'NavBar',
};
</script>

<style scoped>
.navbar {
  width: 100vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: auto;
}

h1 {
  font-family: var(--font-cursive);
  font-size: 2.5rem;
  color: var(--verde-botanico);
}

.navbar__menu,
.navbar__search,
.navbar__user {
  height: 1.5rem;
}

.navbar__icon {
  padding: 0 1rem;
}

.navbar__search {
  margin: 0 0.5rem;
}
</style>
