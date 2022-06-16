<template>
  <main class="columns is-gapless is-multiline">
    <div class="colunm is-one-quarter">
    <BarraLateral/>
    </div>
    <div class="column is-three-quarter">
      <FormularioComponent/>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from "@/components/BarraLateral.vue";
import FormularioComponent from "@/components/Formulario.vue";

export default defineComponent({
  name: 'App',
  components: {
    FormularioComponent,
    BarraLateral
  }
});
</script>

<style>
</style>
