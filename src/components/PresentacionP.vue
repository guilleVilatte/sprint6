<template>
<div class="presentacion">
    <h1>Bienvenido al pryecto numero uno con Vue</h1>
    <button @click="$emit('iniciar')">Iniciar</button>
</div>
</template>

<script>
export default{
    name: 'PresentacionP'
}

</script>

<style>
    .presentacion{
        text-align: center;
        margin-bottom: 50px;
    }
</style>