<template>
    <div>
        


      <el-container>
            <el-aside id="Left_aside" width="25%">
            Left_Aside
            
            </el-aside>
            <el-main>
              
              <!-- Main -->

               <!-- {{newsInfo}} -->
               
               <!-- <ul>
                  <li v-for="(data , index) in newsInfo" :key="index">
                      {{data.name}}: {{data.settlePrice}}<b> {{data.responseTime}}</b>

                  </li>
               </ul> -->

               <div v-for="(data , index) in newsInfo" :key="index">
                    <SingleNewsInfoComponent :content="data" :newsType="true" ></SingleNewsInfoComponent>
               </div>

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
            value:0,
            tmpNewsInfo:[],
            ajaxResponsetime:''
        }
    },
    methods:
    {
       getData()
       {
            myAxios.get("https://quote.cnbc.com/quote-html-webservice/quote.htm?noform=1&partnerId=2&fund=1&exthrs=0&output=json&symbols=@DJ.1|@SP.1|@ND.1|@CL.1|US10Y&requestMethod=quick")
            .then( res=>(  this.newsInfo = res.data.QuickQuoteResult.QuickQuote

            )) ; 


            //console.log( "newsInfo", this.newsInfo);
            //console.log( "tmpNewsInfo", this.tmpNewsInfo);
            this.newsInfo.push(this.newsInfo[0]);
            this.newsInfo.pop();
            //this.newsInfo = this.newsInfo.concat(this.tmpNewsInfo) ;


            //alert("number of elements"+this.newsInfo.length );
       },

       init()
       {
            myAxios.get("https://quote.cnbc.com/quote-html-webservice/quote.htm?noform=1&partnerId=2&fund=1&exthrs=0&output=json&symbols=@DJ.1|@SP.1|@ND.1|@CL.1|US10Y&requestMethod=quick")
                    .then( res=>(  this.newsInfo = res.data.QuickQuoteResult.QuickQuote

            )) ; 

            clearInterval(this.timerId);
            this.timerId = window.setInterval(this.getData,2000);
       }


    },
    mounted() {
     

        //alert("start init");
        this.init() ;
        //alert("end init");
      
      
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