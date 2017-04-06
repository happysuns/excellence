<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<script>
  import VLink from '../components/VLink' /*引用跳转封装*/
  export default {
    components: {
      VLink
    }
  }
</script>

<style lang="scss">
/*清楚默认样式*/
@import "../components/main";
//引用变量、方法
@import "../components/mixin";
html{ font-size: 62.5%; }
</style>
