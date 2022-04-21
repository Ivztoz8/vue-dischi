<template>
    <div class="container-fluid py-5">
        <div class="row row-cols-5 text-white g-2">
            <CardDisco v-for="(element, index) in dischi" 
            :key="index" :poster="element.poster" :title="element.title" :author="element.author" :year="element.year"
            />
        </div>
    </div>
  
</template>

<script>

import axios from 'axios'
import CardDisco from './sons/CardDisco.vue'

export default {
  name: 'DiscGrid',
  components: {
      CardDisco 
  },
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

</style>
