
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BarraLateral",
  emits: ["aoTemaAlterado"],
  data() {
    return {
      modoEscuroAtivo: false,
    };
  },
  methods: {
    alterarTema() {
      this.modoEscuroAtivo = !this.modoEscuroAtivo;
      this.$emit("aoTemaAlterado", this.modoEscuroAtivo);
    },
  },
  computed: {
    textoBotao() {
      if (this.modoEscuroAtivo) {
        return "Desativar modo escuro";
      }
      return "Ativa modo escuro";
    },
  },
});
</script>

<template>
  <header>
    <h1><img src="../assets/logo.png" alt="" /></h1>
    <button class="button" @click="alterarTema">{{ textoBotao }}</button>
  </header>
</template>

<style scoped>
header {
  padding: 1rem;
  color: var(--texto-primario-alt);
  background-color: var(--bg-primario-alt);
  width: 100%;
  height: 100vh;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
