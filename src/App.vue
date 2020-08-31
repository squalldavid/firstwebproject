<template>
  <div id="app">
 
   <!-- {{StockQuote}} -->
    
    <el-container>
      <el-header id="myheader" height="200px">
        <Br_head> </Br_head>
      </el-header>
    </el-container>

    <NavBar :MenuItems="menuInfo"></NavBar>

    <!-- <MainPage :myInfo="StockQuote"></MainPage> -->
    <router-view/> 

     

  </div>
</template>



<script>
import br_head from './components/br_head.vue'
import nav_bar from "./components/navbar.vue"

import myPage  from './components/HelloWorld.vue'
export default {
  name: 'App',

  components:
  {
      Br_head: br_head,
      NavBar: nav_bar,
      MainPage: myPage,
      timerID:''
      
  },

  data()
    {
      return{
        testmsg: "Hello world!",
        menuInfo:[
            {id:1, name: "Front Page"},
            {id:2, name: "Finance"},
            {id:3, name: "Politics"},
            {id:4, name: "Sports"}
        ],
        StockQuote:[],
        value:0      
      }
    
    },
  methods:
  {
    // // getData()
    // // {
    // //   this.value ++ ;
    // //   console.log(this.value); 
    // // }
  }
  // mounted()
  // {
  //     clearInterval(this.timerId)
  //     this.timerId = window.setInterval(this.getData,1000);
  // }


}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0px;
  padding: 0px;
  border: 0px;
}

#myheader{
  //float:left;
  padding: 0px
}

#Left_aside
{
  background-color: coral;

}
#Right_aside
{
  background-color: blue;

}


*{
  
  margin: 0px;
  padding: 0px;
}

</style>
