<template>
<div>
    <button @click="$emit('click1')">Siguiente</button>
    <button @click="$emit('click2')">Anterior</button>
</div>
</template>

<script>
export default{
    name: 'BotonS'
}

</script>

<style scoped>
    div{
        width: 100%;
    }
    button{
        width: 50%;
        height: 50px;
    }
</style>