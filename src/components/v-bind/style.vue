<template>
  <div>
     <div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>

     <div v-bind:style="[baseStyles, overridingStyles]"></div>

     <div v-bind:style="styleObject"></div>
  </div>
</template>
<script>
export default {
  name: "",
  data: {
    activeColor: "red",
    fontSize: 30,
    styleObject: {
      color: "red",
      fontSize: "13px"
    }
  }
};
</script>
