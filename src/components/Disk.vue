<template>
  <section>
      <div class="disk">
        <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
        <h3>NEW JERSEY</h3>
        <div>
           <span>Bon Jovi</span> 
           <span>1988</span> 
        </div>
      </div>
  </section>
</template>

<script>
export default {
  name: 'Disk',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section{
    display: flex;
    flex-wrap: wrap;
}
.disk{
    width: calc((100% / 5) - 2rem);
    // padding: 1rem;
    background-color: #2e3a46;
    margin: 1rem;
    text-align: center;

    img{
        max-width: 100%;
        padding: 1rem;
    }
    h3{
        color: #fff;
        font-size: .8rem;
        padding: 0 1rem;
    }
    div{
        color: #6d6a69;
        padding: .7rem 0;
        font-size: .8rem;
        span{
            display: block;
        }
    }
}
</style>
