<template>
    <div class="container-fluid py-5">
        <div class="row row-cols-5 text-white g-2">
            <CardDisco v-for="(element, index) in filteredDisc" 
            :key="index" :card="element"/>
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
  props:{
      passaGenSelProps: String
  },
  computed:{
      filteredDisc(){
          if(this.passaGenSelProps == ''){
              return this.dischi
          } else {
              return this.dischi.filter( (el) => {
                  return el.genre.includes(this.passaGenSelProps)
              })
          }
      }
  },
  data(){
      return{
          dischi: [],
          generi: []
      }
  },
  created(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then( (res) => {
          this.dischi = res.data.response

          this.dischi.forEach( (element) => {
              if (!this.generi.includes(element.genre))
              this.generi.push(element.genre)

          this.$emit('generiPronti', this.generi)    
          })
      })
  }
}
</script>


<style scoped lang="scss">

</style>
