<template>
  <div id="app">
    {{msg}}
    <router-view></router-view>
  </div>
</template>

<style lang="less">

</style>
<script>
export default {
  name:"app",
  data:function(){
    return {
       msg:"hello world"
    }
  }
}
</script>
