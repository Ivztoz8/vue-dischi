<template>
  <div>
    <div class="col text-center mb-5">
      <div class="bg-card pb-3"> 
        <img :src="card.poster" alt="" class="img-fluid my-3 mt-0">
        <h3 class="my-3">{{card.title}}</h3>
        <h4 class="text-white-50 my-3">{{card.author}}</h4>
        <h4 class="text-white-50 my-3">{{card.year}}</h4>
      </div>
       
    </div> 
  </div>
</template>

<script>
export default {
  name: 'CardDisco',
  props:['card']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/index.scss';

.bg-card{
    background-color: $header-bg;
}

</style>
