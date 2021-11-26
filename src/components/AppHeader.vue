<template>
  <header>
      <div id="logo">
          <img src="../assets/img/logo.png" alt="logo-spotify">
      </div>
  </header>
</template>

<script>
export default {
  name: 'AppHeader',
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header{
    background-color: #2e3a46;
    height: 100px;
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
