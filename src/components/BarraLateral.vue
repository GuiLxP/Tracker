<template>
  <header>
    <h1>
      <img src="../assets/logo.png" alt="logoApplication Tracker">
    </h1>
    <button class="button" @click="alterarTema">
      {{textoBotao}}
    </button>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
//componente da barra
export default defineComponent({
  name: "BarraLateral",
  emits: [ 'aoTemaAlterado' ],
  data() {
    return {
      modoEscuroAtivo: false,
      // estilos: {
      //   background: '#0D3B66';
      //   width: '100%'
      //   height: '100vh',
      //   padding: '1rem',
      //   textAlign: 'center',
      // }
    }
  },
  computed: {
    textoBotao() {
      if (this.modoEscuroAtivo) {
        return 'Modo claro'
      }
      else {
        return 'Modo escuro'
      }
    },
  },
  methods: {
    alterarTema() {
      this.modoEscuroAtivo = !this.modoEscuroAtivo
      this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
    },
  }
});
</script>

<style scoped>
header {
  background: #0D3B66;
  width: 100%;
  height: 100vh;
  padding: 1rem;
  text-align: center;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>