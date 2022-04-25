<template>
  <div id="app">
      <CMPHeader
      :passaGeneriProps="generi"
      @inviaGenereSel="ottieniGenereSel"/>
      <DiscGrid
      @generiPronti="ottieniGeneri"
      :passaGenSelProps="genereSelezionato"/>
  </div>
</template>

<script>
import "bootstrap"
import CMPHeader from './components/CMPHeader.vue'
import DiscGrid from './components/DiscGrid.vue'

export default {
  name: 'App',
  components: {
    CMPHeader,
    DiscGrid
  },
  data(){
    return{
      generi: [],
      genereSelezionato: ''
    }
  },
  methods:{
    ottieniGeneri(mieiGeneri){
      this.generi = mieiGeneri
    },
    ottieniGenereSel(genSel){
      this.genereSelezionato = genSel
    }
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
@import './components/style/index.scss';

body{
  background-color: $bg-body;
}

header{
    background-color: $header-bg;
    padding: 30px;
  }


</style>
