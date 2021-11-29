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
          selectedOption: null,
      }
  },
  methods: {
      selectOption(event) {
          this.selectedOption = event.target.value;
          console.log(this.selectedOption);
          return "$emit('choose', this.selectedOption)"
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
