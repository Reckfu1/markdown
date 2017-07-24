<template>
  <div id="app"> 
    <img src="./assets/logo.png" alt="">
    <span>Vue Markdown</span>
    <editor></editor>
  </div>
</template>

<script>
import editor from './components/editor'
export default {
  name: 'app',
  components: {
    editor 
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  height: 100%;
  width:100%;
}
#app img{
  height: 100px;
  width:100px;
  margin-top:10px;
}
#app span{
  font-size: 35px;
  position: relative;
  top:-30px;
  font-weight:bold;
}
</style>
