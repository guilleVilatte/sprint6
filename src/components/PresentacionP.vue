<template>
  <div class="presentacion">
    <h1>Bienvenido al pryecto numero uno con Vue</h1>
    <div class="boton">
      <button @click="$emit('iniciar')">Iniciar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "PresentacionP",
};
</script>

<style scoped>
.boton {
  text-align: center;
}
h1 {
  color: pink;
  text-align: center;
}

</style>