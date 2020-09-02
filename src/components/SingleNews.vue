<template>
<div :class="'newsType'?'Important':'Normal'">
  <p>

       {{content.name}}: {{content.settlePrice}}<b> {{content.responseTime}}</b>  
       <span> <a href="#">More...</a> </span>
         
</p>


</div>

</template>

<script>
export default {
    props:
    {
        content:
        {
            type: Object
        },
        newsType: false
    }

}
</script>

<style>
div{
    //height: 50px;
    padding: 2px;
    margin-left: 1px;
    font-size: x-small;
    text-align: left;
    box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);

}
a{
    font-style:italic;
}
a:hover{
    background-color: yellow;
    color: cornflowerblue;
    font-size: medium;
}
.Important
{
    color: red;
}
.Normal{
    color: black;
}

</style>