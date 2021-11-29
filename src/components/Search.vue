<template>
      <section>
            <label for="discs">Filtra Albums per genere:</label>
            <select name="discs" id="discs" @change="selectOption">
                <option selected disabled>Seleziona un'opzione</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
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
  methods: {
      selectOption(event) {
          this.selectedOption = event.target.value;
        //   console.log(this.selectedOption);
          this.$emit('choose', this.selectedOption);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    section{
        width: 100%;
        color: #fff;
        font-size: 1.5rem;
        padding-top: 2rem;
        text-align: center;
        #discs{
            padding: 0 1rem;
        }
    }
</style>
