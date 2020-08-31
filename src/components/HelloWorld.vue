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
                  <li v-for="(data , index) in newsInfo" :key="index">
                      {{data.name}}: {{data.settlePrice}}<b> {{data.responseTime}}</b>
                      <!-- <SingleNewsInfoComponent ></SingleNewsInfoComponent> -->
                  </li>

               </ul>

            </el-main>
            <el-aside id="Right_aside" width="25%">Right_Aside</el-aside>
    </el-container>
             
    </div>
</template>

<script>
import myAxios from 'axios'
import SingleNewsInfo from './SingleNews.vue'

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
        SingleNewsInfoComponent:SingleNewsInfo
    },
    data(){
        return{

            newsInfo:[],
            timerId:'',
            value:0
        }
    },
    method:
    {
       getData()
       {
         this.value += 11 ;
         console.log(this.value);
       }
    },
    mounted() {
     
      myAxios.get("https://quote.cnbc.com/quote-html-webservice/quote.htm?noform=1&partnerId=2&fund=1&exthrs=0&output=json&symbols=@DJ.1|@SP.1|@ND.1|@CL.1|US10Y&requestMethod=quick")
            .then( res=>(  this.newsInfo = res.data.QuickQuoteResult.QuickQuote

      )) ; 

      clearInterval(this.timerId)
      this.timerId = window.setInterval(function(){
        
        // this.value ++ ;  
        // console.log(this.value);

        myAxios.get("https://quote.cnbc.com/quote-html-webservice/quote.htm?noform=1&partnerId=2&fund=1&exthrs=0&output=json&symbols=@DJ.1|@SP.1|@ND.1|@CL.1|US10Y&requestMethod=quick")
        .then( res=>(  this.newsInfo = res.data.QuickQuoteResult.QuickQuote

        )) ; 



       alert(this.newsInfo[0].responseTime );
     
        var tmp = this.newsInfo[0] ;

        this.newsInfo.push(tmp) ;
        this.newsInfo.pop() ;

        
      },2000);

      
      
    },
    created()
    {

    },
    beforeMount()
    {

    },
    beforeDestroy() {
      clearInterval(this.timerId);
      this.timerId = null;
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