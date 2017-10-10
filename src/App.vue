<template>
  <div id="app">
    <navmenu v-show="navshow"/>
    <router-view/>
  </div>
</template>

<script>
import NavMenu from '@/components/NavMenu'
export default {
  name: 'app',
  data(){
    return {
      navshow:true
    }
  },
  modules(){

  },
  created(){
      this.NavShow()
  },
  methods:{
      NavShow(){
        if(this.$route.path == '/login'){
            this.navshow = false
          }else{
            this.navshow = true
          }
      }
  },
  components:{
    navmenu:NavMenu
  },
  weach:{
     'navshow':'NavShow'
  }
}
</script>

<style>
*{
  padding:0px;
  margin:0px;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
