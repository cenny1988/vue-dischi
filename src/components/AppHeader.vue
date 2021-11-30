<template>
  <header>
      <div id="logo">
          <img src="../assets/img/logo.png" alt="logo-spotify">
      </div>

      <!-- select component -->
      <Search @change="$emit('changeGen', chooseUser)" @choose="searching" :options="listGenres"/>
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
          this.chooseUser = valChoose;
          console.log('log di chooseUser: ',this.chooseUser);
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
