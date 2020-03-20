<template>
  <div id="app">
    <keep-alive include="broad">
    <router-view/>
    <tabber :ishow="bol"></tabber>
  </div>
</template>

<script>
import Tabbar from '../src/components/tabber' 
import Jquery from 'jquery'
export default {
  name: 'App',
  components:{
    Tabbar
  },

  data() {
    return {
      bol:true
    }

  },

  watch:{
    '$route':function(to,from){
      let arr=['/home','/mine']
      if(arr.includes(to.path)){
        this.bol=true
      }else{
        this.bol=false
      }
    }
  },







}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
