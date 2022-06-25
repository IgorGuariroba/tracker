<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <Cronometro :tempo-em-segundos="tempoEmSegundos"/>
    <Botao :nameButton="nameButton1" @clickEvent="iniciar" :cronometro-rodando="cronometroRodando"/>
    <Botao :nameButton="nameButton2" @clickEvent="finalizar" :cronometro-rodando="!cronometroRodando"/>
  </div>
</template>

<script lang="ts">
import Cronometro from "@/components/Cronometro.vue";
import {defineComponent} from "vue";
import Botao from "@/components/Botao.vue";

export default defineComponent({
  name: "Temporizador",
  emits: ['aoTemporizadorFinalizado'],
  components: {Cronometro, Botao},
  data() {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
      cronometroRodando: false,
      nameButton1: "Play",
      nameButton2: "Stop"
    }
  },
  methods: {
    iniciar() {
      this.cronometroRodando = true
      this.cronometro = setInterval(() => {
        this.tempoEmSegundos += 1
      }, 1000)
    },
    finalizar() {
      this.cronometroRodando = false
      clearInterval(this.cronometro)
      this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos)
      this.tempoEmSegundos = 0
    }
  }
})
</script>

<style scoped>

</style>