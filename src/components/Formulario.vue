<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Fomulário para criação de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual terefa você deseja iniciar?"
               v-model="descricao"
        >
      </div>
      <div class="column">
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";
import Temporizador from "@/components/Temporizador.vue";

export default defineComponent({
  name: "FormularioComponent",
  components: {Temporizador},
  emits:['aoSalvarTarefa'],
  data() {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      this.$emit('aoSalvarTarefa',{
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao
      })
      this.descricao = ''
    }
  }
})
</script>

<style scoped>

</style>