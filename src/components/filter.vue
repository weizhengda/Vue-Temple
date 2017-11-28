<template>
  <div id="filter">
     {{message | filters2| filters3(true,priceCount)}}
  </div>
</template>
<script>
export default {
  el: "#filter",
  data: {
    message: 199,
    priceCount:.8
  },
  filters:{
    filters2:function (arg) {
      console.log("arg:"+arg)
      if(arg>100){
        return arg-8;
      }else {
        return arg;
      }
    },
    filters3:function (arg_1,arg_2,arg_3) {
      var result;
      console.log("arg_1:"+arg_1)
      console.log("arg_2:"+arg_2)
      console.log("arg_3:"+arg_3)
      if(arg_2){
        result = arg_1*arg_3;
        console.log("result"+result);
        return result;
      }else{
        result =arg_1;
        console.log("result"+result);
        return result
      }
 
    }
  }
}
</script>
