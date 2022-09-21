<template>
  <div class="cuerpo" :style="fondo">
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
    <h2 v-else>Este es el primer proyecto con Vue utilizando las primeras propiedades</h2>
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
        {
          frase:"Nuestro héroe estaba flotando por el espacio sideral cuando a lo lejos divisó una nave espacial",
          imagen:"url(../../img/1.jpg)"
        },
        {
          frase:"Sentía curiosidad por el interior de la nave y se puso a inspeccionarla. Llegó a una sala con dos puertas.",
          imagen:"url(../../img/2.jpg)"
        },
        {
          frase:"El héroe decidió atravesar la puerta que le llevaba a casa",
          imagen:"url(../../img/3.jpg)"
        },
        {
          frase:"Mientras tanto, otros héroes no tuvieron tanta suerte en su elección...",
          imagen:"url(../../img/4.jpg)"
        }
      ],
      postCurrentSentence: null,
      start: false,
      fondo: {backgroundImage:""}
    };
  },
  methods: {
    next() {
      if (this.postCurrentSentence < 3) {
        document.querySelectorAll(".caja")[0].style.backgroundColor =
          "rgba(255, 254, 254, 0.7)";
        this.postCurrentSentence++;
        this.fondo.backgroundImage = this.postFrases[this.postCurrentSentence].imagen;
      } else {
        this.postCurrentSentence = 0;
        document.querySelectorAll(".caja")[0].style.backgroundColor = "pink";
        this.fondo.backgroundImage = this.postFrases[this.postCurrentSentence].imagen;
      }
    },
    before() {
      if (this.postCurrentSentence > 0) {
        this.postCurrentSentence--;
        document.querySelectorAll(".caja")[0].style.backgroundColor =
          "rgba(255, 254, 254, 0.7)";
          this.fondo.backgroundImage = this.postFrases[this.postCurrentSentence].imagen;
      } else {
        this.postCurrentSentence = 3;
        document.querySelectorAll(".caja")[0].style.backgroundColor =
          "rgba(255, 254, 254, 0.7)";
          this.fondo.backgroundImage = this.postFrases[this.postCurrentSentence].imagen;
      }
      if (this.postCurrentSentence == 0) {
        document.querySelectorAll(".caja")[0].style.backgroundColor = "pink";
      }
    },
    iniciar() {
      if (this.start == false) {
        this.start = true;
        this.postCurrentSentence = 0;
      } else {
        this.start = false;
      }
    },
  },
};
</script>

<style scoped>
.botones {
  margin-top: 30px;
  margin-left: 20px;
  margin-right: 20px;
  display: flex;
  justify-content: center;
}
.cuerpo {
  background-image:url(../../public/img/1.jpg);
  background-repeat: no-repeat;
  background-position: center;
  background-attachment: fixed;
  background-size: cover;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
}
h2 {
  margin: auto;
  border-radius: 8px;
  margin-top: 30vh;
  width: 70%;
  background: black;
  color: greenyellow;
  text-align: center;
}
</style>