<template>
    <div class="container py-5">
        <div class="row row-cols-6 text-white text-center g-4">
            <div class="text-center bg-card mx-3" v-for="(element, index) in dischi" :key="index">
                <img :src="element.poster" alt="" class="img-fluid my-3">
                <h3 class="my-3">{{element.title}}</h3>
                <h4 class="text-white-50 my-3">{{element.author}}</h4>
                <h4 class="text-white-50 my-3">{{element.year}}</h4>
            </div>
        </div>
    </div>
  
</template>

<script>

import axios from 'axios'

export default {
  name: 'DiscGrid',
  data(){
      return{
          dischi: []
      }
  },
  created(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then( (res) => {
          this.dischi = res.data.response
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

@import './style/index.scss';

.bg-card{
    background-color: $header-bg;
}

</style>
