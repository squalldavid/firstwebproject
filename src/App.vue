<template>
  <div id="app">
    
    <!--<router-view/>-->

    <el-container>
      <el-header id="header" height="200px">Header</el-header>
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
export default {
  name: 'App'
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
   background-position: center;

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
