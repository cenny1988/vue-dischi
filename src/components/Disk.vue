<template>
      <div class="disk">
        <img :src="details.poster" :alt="details.title">
        <h3>{{details.title}}</h3>
        <div>
           <span>{{details.author}}</span> 
           <span>{{details.year}}</span> 
        </div>
      </div>
</template>

<script>
export default {
  name: 'Disk',
  props: {
    details: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.disk{
    width: calc((100% / 5) - 1.6rem);
    background-color: #2e3a46;
    margin: .7rem .8rem;
    text-align: center;

    img{
        max-width: 100%;
        padding: 1rem;
        aspect-ratio: 1;
    }
    h3{
        color: #fff;
        font-size: .8rem;
        padding: 0 1rem;
        text-transform: uppercase;
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
