<template>
  <div>
  
    <div v-bind:class="{ active: isActive }"></div>
  
    <div class="static" v-bind:class="{ active: isActive, 'text-danger': hasError }"></div>
  
    <div v-bind:class="classObject"></div>

  </div>
</template>
<script>
export default {
  name: "",

  data: {
    // 第一种写法
    isActive: true,

    hasError: false,
    // 第二种写法
    classObject: {
      active: true,
      "text-danger": false
    }
  },
  computed: {
    // 第三种写法
    classObject: function() {
      return {
        active: this.isActive && !this.error,
        "text-danger": this.error && this.error.type === "fatal"
      };
    }
  }
};
</script>
<style scoped>
.active {
  color: red;
}
</style>

