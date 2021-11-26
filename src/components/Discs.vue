<template>
  <section class="container">
      <Disk v-for="disk, i in discs.response" :key="i" :details="disk"/>
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
          })
      }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container{
    display: flex;
    flex-wrap: wrap;

    width: 70%;
    margin: 0 auto;
    padding: 3rem 0;
}
</style>
