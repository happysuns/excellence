<!-- 这个是公用的头部组件 -->
<template>
  <div id="Resume_header">
    <header>
      <img class="h_img" src="../assets/h_logo.png">
      <span class="tas_title" v-show="title">{{title}}</span>
    </header>
  </div>
</template>
<script>
export default {
  props: ['title'],
  data: function(){
    return{
    }
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Resume_header{
  header{
    padding: 3%;
    overflow: hidden;
    background: $color-blue;
    .h_img{
      width: 45%;
      height: auto;
    }/*logo*/
    .tas_title{
      position: absolute;
      top: 4%;
      right: 7%;
      font-size: 1.5rem;
      font-weight: 700;
      color: $color-gray;
    }
  }/*头部*/
}
</style>