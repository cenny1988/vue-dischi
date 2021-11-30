<template>
  <div id="app">
    <AppHeader @changeGen="getChoose" :listGenres="genersAlbums"/>
   
    <Discs @loadGenre="getGenre" :selectGen="selChoose" />
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
  },
  data(){
      return{
          genersAlbums: [],
          selChoose: '',
      }
  },
  methods: {
    getGenre(listsGenre){
      this.genersAlbums = listsGenre;
      // console.log(this.genersAlbums);
    },
    getChoose(genreChoose){
      this.selChoose = genreChoose;
      console.log('log di selCoose: ',this.selChoose);
    }
  },
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {

}
</style>
