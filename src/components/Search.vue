<template>
      <section>
            <label for="discs"> Filtra Albums per genere:</label>
            <select id="discs" @change="$emit('choose', $event.target.value)">
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
          selectedOption: '',
      }
  },
  props: {
    options: Array,
    
  },
  methods: {
    //   se utilizzo qst il seguente metodo --> rig4: @change="selectOption"
    //   selectOption(event) {
    //       this.selectedOption = event.target.value;
    //       this.$emit('choose', this.selectedOption);
    //   },
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
            border-radius: 10px;
        }
    }
</style>
