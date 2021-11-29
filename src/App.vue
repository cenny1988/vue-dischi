<template>
  <div id="app">
    <AppHeader/>
    <main>
      <Discs/>
    </main>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import Discs from './components/Discs.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    Discs,
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  main{
    background-color: #1e2d3b;
  }
  
}
</style>
