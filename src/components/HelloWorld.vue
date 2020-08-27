<template>
    <div>
        


      <el-container>
            <el-aside id="Left_aside" width="25%">
            Left_Aside
            
            </el-aside>
            <el-main>
              
              <!-- Main -->

               <!-- {{newsInfo}} -->
               <ul>
                  <li v-for="data in newsInfo.QuickQuoteResult.QuickQuote" :key="data.symbol">
                      {{data.name}}: <b> {{data.settlePrice}}</b> {{data.responseTime}}
                  </li>

               </ul>

            </el-main>
            <el-aside id="Right_aside" width="25%">Right_Aside</el-aside>
    </el-container>
             
    </div>
</template>

<script>
import myAxios from 'axios'

export default {
    
    props:
    {
      myInfo:
      {
        type:Object
      }
    },
    components:
    {
        
    },
    data(){
        return{

            newsInfo:[]
        }
    },
  mounted() {
    myAxios.get("https://quote.cnbc.com/quote-html-webservice/quote.htm?noform=1&partnerId=2&fund=1&exthrs=0&output=json&symbols=@DJ.1|@SP.1|@ND.1|@CL.1|US10Y&requestMethod=quick")
           .then( res=>(  this.newsInfo = res.data

    ))    
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