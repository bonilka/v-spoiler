<template>
  <DemoPage />
</template>

<script lang="ts">
import { defineComponent,computed } from 'vue';
import DemoPage from './pages/DemoPage.vue'
import './styles/global.css'

export default defineComponent({
  name: 'App',
  components: {
    DemoPage
  },
  data() {
    return {
      isInverse: false
    }
  },
  provide() {
    return {
      setTheme: (isInverse: boolean) => {
        this.isInverse = isInverse;
        document.body.classList.toggle('theme-inverse', this.isInverse);
      },
      isThemeInverse: computed(() => this.isInverse)
    };
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
  max-width: 760px;
  margin: auto;
}
</style>
