<template>
  <section>
      <div v-if="loading"> Loading... </div>
      <div v-else id="container">
        <Disk v-for="disk, i in discs.response" :key="i" :details="disk"/>
      </div>
  </section>
</template>

<script>
import Disk from '../components/Disk.vue';
import axios from 'axios';

export default {
  name: 'Discs',
  components: {
    Disk,
  },
  data(){
      return{
          loading: true,
          apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
          discs: {},
      }
  },
  created() {
      this.getDiscs();
  },
  methods: {
      getDiscs(){
          axios
          .get(this.apiUrl)
          .then((result) => {
              this.discs = result.data;
              this.loading = false;
          })
        //   metodo catch per catturare gli errori
          .catch((errore) => {
              console.log("Errore: ", errore);
          })
      }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section{
    text-align: center;
    color: #fff;
    font-size: 4rem;
}
#container{
    display: flex;
    flex-wrap: wrap;

    width: 70%;
    margin: 0 auto;
    padding: 3rem 0;
}
</style>
