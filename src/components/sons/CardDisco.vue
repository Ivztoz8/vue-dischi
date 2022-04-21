<template>
  <div>
    <div class="col text-center bg-card">
        <img :src="poster" alt="" class="img-fluid my-5">
        <h3 class="my-1">{{title}}</h3>
        <h4 class="text-white-50 my-2">{{author}}</h4>
        <h4 class="text-white-50 my-2">{{year}}</h4>
    </div> 
  </div>
</template>

<script>
export default {
  name: 'CardDisco',
  props:{
      poster: String,
      title: String,
      author: String,
      year: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/index.scss';

.bg-card{
    background-color: $header-bg;
}

</style>
