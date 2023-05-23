<template>
  <div id="app">
    <ZoomApp />
  </div>
</template>

<script>
import ZoomApp from './components/ZoomApp.vue'

export default {
  name: 'App',
  components: {
    ZoomApp
  }
}
</script>

<style>
#app {
  width: 70%;
  margin: auto;
  text-align: center;
}
#zmmtg-root {
  display: none;
}
</style>
