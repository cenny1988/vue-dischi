<template>
      <section>
            <!-- <label for="discs"> Filtra Albums per genere:</label> -->
            <select id="discs" @change="selectOption">
                <option selected disabled>Seleziona un'opzione</option>
                <option value="All">All</option>
                <option 
                    v-for="option,i in options" 
                    :key="i" 
                    :value="option"
                >
                    
                    {{option}}
                </option>
        </select>
      </section>
</template>

<script>
export default {
  name: 'Search',
  data(){
      return{
          selectedOption: null,
      }
  },
  props: {
    options: Array,
    
  },
  methods: {
      selectOption(event) {
          this.selectedOption = event.target.value;
          this.$emit('choose', this.selectedOption);
      },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    section{
        // width: 100%;
        color: #fff;
        font-size: 1.5rem;
        padding-top: 2rem;
        text-align: center;
        margin: 0 2rem;
        #discs{
            padding: 5px 1rem;
        }
    }
</style>
