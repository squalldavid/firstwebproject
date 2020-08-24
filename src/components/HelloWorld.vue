<template>
    <div>
        


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


export default {

    components:
    {
        
    },
    data(){
        return{

            
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