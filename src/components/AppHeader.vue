<template>
  <header>
      <div id="logo">
          <img src="../assets/img/logo.png" alt="logo-spotify">
      </div>

      <!-- select component -->
      <Search  @choose="searching" :options="listGenres"/>
  </header>
</template>

<script>
import Search from '../components/Search.vue';

export default {
  name: 'AppHeader',
  props: {
      listGenres: Array,
  },
  components: {
    Search
  },
  data() {
      return {
          chooseUser: '',
      }
  },
  methods: {
      searching(valChoose){
          //   salvo il valore ricevuto dal child (ovvero Search),
          this.chooseUser = valChoose;
        //   ... e lo invio con $emit al parent
          this.$emit('changeGen',this.chooseUser)
        // in alternativa posso cancellare riga 33, e a riga 8 posso aggiungere
        // :childToParent="$emit('changeGen', chooseUser)"
      }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header{
    background-color: #2e3a46;
    height: 100px;
    display: flex;
    justify-content: space-between;
    #logo{
        width: 100px;
        padding: 1rem;
        img{
            max-width: 100%;
            object-fit: contain;
        }
    }
}
</style>
