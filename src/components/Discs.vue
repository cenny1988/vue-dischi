<template>
  <section>
       <!-- loading -->
      <div v-if="loading" id="loading"> 
          <span></span>
          <span></span>
          <span></span>
          <span></span>
      </div>

      <!-- container album -->
      <div v-else id="container">
            <Disk v-for="disk, i in filteredDiscs" 
            :key="i" 
            :details="disk"
        />
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
  props:{
      selectGen: String,
  },
  data(){
      return{
          loading: true,
          apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
          discs: [],
          genre: [],
          
      }
  },
  created() {
      this.getDiscs();
  },
  computed: {
      filteredDiscs(){
          if(this.selectGen === '' || this.selectGen === 'All'){
              return this.discs;
          }
          return this.discs.filter((item) => {
              return item.genre.includes(this.selectGen);
          });
      }
  },
  methods: {
      getDiscs(){
          axios
          .get(this.apiUrl)
          .then((result) => {
              this.discs = result.data.response;
              this.loading = false;

            //   genero l array con i generi non duplicati
            this.discs.forEach(element => {
                if(!this.genre.includes(element.genre)){
                    this.genre.push(element.genre)
                }
            });

            // passo i dati del array genre dal figlio discs al padre app
            this.$emit('loadGenre', this.genre)
          })
        //   metodo catch per catturare gli errori
          .catch((errore) => {
              console.log("Errore: ", errore);
          })
      },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section{
    background-color: #1e2d3b;
    min-height: calc(100vh - 100px);
  }
#loading{
    text-align: center;
    padding-top: 4rem;

    // new animated loader 
    display: block;

    span{
        display: inline-block;
        margin-top: 10px;
        height: 20px;
        width: 20px;
        border-radius: 50%;
        animation: move 1s ease-in-out infinite alternate;

        &:not(:first-child){
            margin-left: 10px;
        }    
    }

    span:first-child{
        background-color: #4285f4;
        animation-delay: .2s;
    }
    span:nth-child(2){
        background-color: #db4437;
        animation-delay: .4s;
    }
    span:nth-child(3){
        background-color: #f4b400;
        animation-delay: .6s;
    }
    span:nth-child(4){
        background-color: #0f9d58;
        animation-delay: .8s;
    }
}

@keyframes move {
    to {
        transform: translateY(5px);
    }
    from {
        transform: translateY(-10px);
    }

}



#container{
    display: flex;
    flex-wrap: wrap;

    width: 70%;
    margin: 0 auto;
    padding: 3rem 0;
}
</style>
