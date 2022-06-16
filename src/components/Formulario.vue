<template>
  <div class="box">
    <div class="columns">

      <div class="column is-8" role="form" aria-label="Fomulário para criação de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual terefa você deseja iniciar?">
      </div>

      <div class="column">
        <div class="is-flex is-align-items-center is-justify-content-space-between">
          <select>
            <strong>00:00:00</strong>
          </select>
          <button class="button">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: "FormularioComponent"
})
</script>

<style scoped>

</style>