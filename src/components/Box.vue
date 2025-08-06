
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BoxComponent",
  data() {
    return {
      estilos: {
        color: "var(--texto-primario-alt)",
        backgroundColor: "var(--bg-primario-alt)",
      },
    };
  },
});
</script>

<template>
  <div class="box has-text-weight-bold" :style="estilos">
    <slot></slot>
  </div>
</template>

<style scoped>
.box * {
  color: var(--texto-primario) !important;
}
</style>