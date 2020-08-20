<template>
  <div id="app">
 
    <!--<router-view/>-->
    
    <el-container>
      <el-header id="header" height="200px">
        <Br_head> </Br_head>
      </el-header>
      <el-container>
        <el-aside id="Left_aside" width="25%">
          Left_Aside
          <img src="./assets/logo.png" alt="">
          <img src="./assets/logo.png" alt="">
          <img src="./assets/logo.png" alt="">
          <img src="./assets/logo.png" alt="">
        </el-aside>
        <el-main>Main</el-main>
        <el-aside id="Right_aside" width="25%">Right_Aside</el-aside>
      </el-container>
    </el-container>

     

  </div>
</template>



<script>
import br_head from './components/br_head.vue'

export default {
  name: 'App',

  components:
  {
      Br_head: br_head
  }

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
#header
{
   background-image: url("./assets/logo.png");
   background-repeat: no-repeat;
   background-position: left;

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
