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