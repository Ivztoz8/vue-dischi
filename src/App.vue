<template>
  <div id="app">
      <CMPHeader/>
      <DiscGrid/>
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
