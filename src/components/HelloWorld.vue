<template>
    <div>
        <NavBar :MenuItems="menuInfo"></NavBar>


      <el-container>
            <el-aside id="Left_aside" width="25%">
            Left_Aside
            
            </el-aside>
            <el-main>Main</el-main>
            <el-aside id="Right_aside" width="25%">Right_Aside</el-aside>
    </el-container>
             
    </div>
</template>

<script>
import nav_bar from "./navbar.vue"

export default {

    components:
    {
        NavBar: nav_bar
    },
    data(){
        return{
            menuInfo:[
                {id:1, name: "Front Page"},
                {id:2, name: "Finance"},
                {id:3, name: "Politics"},
                {id:4, name: "Sports"}
            ]
            
        }
    }
}
</script>

<style>
#Left_aside
{
  background-color: coral;

}
#Right_aside
{
  background-color: blue;

}

</style>