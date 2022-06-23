<template>
  <div>
    <PresentacionP class="comienzo" @click="iniciar"></PresentacionP>
    <div v-if="start === true">
      <div class="botones">
        <BotonS @click1="next" @click2="before"></BotonS>
      </div>
      <EscenaA
        class="proyecto"
        :frases="postFrases"
        :currentSentence="postCurrentSentence"
        @click1="next"
        @click2="before"
      ></EscenaA>
    </div>
  </div>
</template>

<script>
import EscenaA from "./EscenaA.vue";
import BotonS from "./BotonS.vue";
import PresentacionP from "./PresentacionP.vue";

export default {
  name: "HomePage",
  components: {
    EscenaA,
    BotonS,
    PresentacionP,
  },
  data() {
    return {
      postFrases: [
        "Nuestro héroe estaba flotando por el espacio sideral cuando a lo lejos divisó una nave espacial",
        "Sentía curiosidad por el interior de la nave y se puso a inspeccionarla. Llegó a una sala con dos puertas.",
        "El héroe decidió atravesar la puerta que le llevaba a casa",
        "Mientras tanto, otros héroes no tuvieron tanta suerte en su elección...",
      ],
      postCurrentSentence: null,
      start: false,
    };
  },
  methods: {
    next() {
      if (this.postCurrentSentence < 3) {
        document.querySelectorAll(".caja")[0].style.backgroundColor = "white";
        this.postCurrentSentence++;
      } else {
        this.postCurrentSentence = 0;
        document.querySelectorAll(".caja")[0].style.backgroundColor = "pink";
      }
    },
    before() {
      if (this.postCurrentSentence > 0) {
        this.postCurrentSentence--;
        document.querySelectorAll(".caja")[0].style.backgroundColor = "white";
      } else {
        this.postCurrentSentence = 3;
        document.querySelectorAll(".caja")[0].style.backgroundColor = "white";
      }
      if (this.postCurrentSentence == 0) {
        document.querySelectorAll(".caja")[0].style.backgroundColor = "pink";
      }
    },
    iniciar() {
      if(this.start==false){
        this.start = true;
        this.postCurrentSentence = 0
      } else {
        this.start = false
      }
    },
  },
};
</script>

<style scoped>
.botones {
  display: flex;
  justify-content: center;
}
</style>