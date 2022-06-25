<template>
  <button class="button"  @click="$emit('clickEvent')" :disabled="cronometroRodando">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
    <span>{{nameButton}}</span>
  </button>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: "Botao",
  props:{
    nameButton: {
      type: String,
      default: ''
    },
    cronometroRodando: {
      type: Boolean,
      default: false
    }
  }
})
</script>

<style scoped>

</style>