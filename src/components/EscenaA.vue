<template>
<div>
  <div class="caja" v-for="(frase,i) in frases" :key="i" :class="{active: i === currentSentence}">{{frase}}</div>
</div>
</template>

<script>

export default {
  name: 'EscenaA',
  props:{
    frases: Array,
    currentSentence: Number
  }
}
</script>

<style scoped>
  .caja{
    border: 2px solid black;
    margin: 20px;
    padding: 10px;
    text-align: center;
    border-radius: 20px;
  }
  .caja:first-child{
    background: pink;
  }
  .active{
    background: pink;
  }

</style>