<template>
  <section class="container">
      <Disk/>
  </section>
</template>

<script>
import Disk from '../components/Disk.vue'

export default {
  name: 'Discs',
  components: {
    Disk,
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container{
    width: 70%;
    margin: 0 auto;
    padding: 3rem 0;
}
</style>
