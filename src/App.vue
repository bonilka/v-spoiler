<template>
  <DemoPage />
</template>

<script>
import DemoPage from './components/DemoPage.vue'
import './styles/global.css'

export default {
  name: 'App',
  components: {
    DemoPage
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 760px;
  margin: auto;
}
</style>
