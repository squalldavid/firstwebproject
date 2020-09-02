<template>
<div :class="'newsType'?'Important':'Normal'">
  <p>

       {{content.name}}: {{content.settlePrice}}<b> {{content.responseTime}}</b>
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
.Important
{
    color: red;
}
.Normal{
    color: black;
}

</style>