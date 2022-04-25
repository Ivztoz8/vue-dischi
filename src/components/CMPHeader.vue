<template>
  <header class="d-flex justify-content-between align-items-center">
         <a href="#"><img src="../assets/img/spotify-512.png" alt="logo"></a>
          <div>
            <label for="" class="form-label text-white me-2">Seleziona un genere</label>
            <select 
              class="form-select-sm" 
              aria-label="Default select example" 
              v-model="selected" 
              @change="$emit('inviaGenereSel', selected)">
            
              <option value="">Tutti i Generi</option>
              <option v-for="(element, index) in passaGeneriProps" :key="index"
                :value="element">
              {{element}}
              </option>
            </select>
          </div>
  </header>
   
</template>

<script>


export default {
  name: 'CMPHeader',
  props:{
    passaGeneriProps: Array,
  },
  data(){
    return{
      selected: ''
    }
  }
}
</script>

<style lang="scss">
@import './style/index.scss';

img{
  width: 80px;
}  
</style>
