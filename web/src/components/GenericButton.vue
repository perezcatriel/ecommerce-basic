<template>
  <button :class="['generic-button', variantClass]" @click="onClick">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'GenericButton',
  props: {
    variant: {
      type: String,
      default: 'default',
    },
    onClick: Function,
  },
  computed: {
    variantClass() {
      return `button-${this.variant}`;
    },
  },
};
</script>

<style scoped>
.generic-button {
  /* Estilos generales para el botón */
  padding: 10px 20px;
  border: 1px solid var(--font-dark);
  background-color: red;
  cursor: pointer;
}

.button-default {
  /* Estilos para la variante "default" del botón */
  background-color: var(--turquesa-magica);
}

.button-primary {
  /* Estilos para la variante "primary" del botón */
  background-color: var(--turquesa-magica);
  color: #fff;
}

/* Agrega más estilos para otras variantes según sea necesario */
</style>
