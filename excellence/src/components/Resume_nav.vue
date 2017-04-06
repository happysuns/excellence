<!-- 这个是公用的导航组件 -->
<template>
  <div id="Resume_nav">
    <nav v-if="this.index === '1'">
      <div class="line"></div>
      <span class="spans spec_span">1</span>
      <span class="spans">2</span>
      <span class="spans">3</span>
      <span class="spans">4</span>
    </nav>
    <nav v-else-if="this.index === '2'">
      <div class="line"></div>
      <span class="spans">1</span>
      <span class="spans spec_span">2</span>
      <span class="spans">3</span>
      <span class="spans">4</span>
    </nav>
    <nav v-else-if="this.index === '3'">
      <div class="line"></div>
      <span class="spans">1</span>
      <span class="spans">2</span>
      <span class="spans spec_span">3</span>
      <span class="spans">4</span>
    </nav>
    <nav v-else-if="this.index === '4'">
      <div class="line"></div>
      <span class="spans">1</span>
      <span class="spans">2</span>
      <span class="spans">3</span>
      <span class="spans spec_span">4</span>
    </nav>
  </div>
</template>
<script>
export default {
  data: function(){
    return{
      text: this.index
    }
  },
  props:['index']
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Resume_nav{
  nav{
    position: relative;
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    width: 100%;
    margin: 5% 0; 
    .line{
      width: 75%;
      position: absolute;
      left: 12%;
      top: 50%;
      height: .1rem;
      background: $color-cyan;
      z-index: -1;
    }/*画线*/
    .spans{
      position: relative;
      flex: 1;
      text-align: center;
      width: 10%;
      padding: 2% 0;
      font-size: 1.2rem;
      color: $color-cyan;
      &:before{
        content: '';
        width: 1.5rem;
        height: 1.5rem;
        display: inline-block;
        position: absolute;
        left: 50%;
        top: 50%;
        margin: -.80rem 0 0 -.8rem;
        border-radius: 50%;
        background: $color-white;
        z-index: -1;
        box-shadow: 0 0 0 .1rem $color-cyan;
      }
      &:after{
        content: '基本信息';
        position: absolute;
        left: 23%;
        bottom: -65%;;
        font-size: 1.3rem;
        color: $color-gray_s;
      }
    }/*所以span的样式*/
    .spans:last-of-type{
      &:after{
        content: '职业偏好';
      }
    }
    .spans:nth-of-type(2){
      &:after{
        content: '学历技能';
      }
    }
    .spans:nth-of-type(3){
      &:after{
        content: '成长经历';
      }
    }
    .spec_span{
      color: $color-white; 
      &:before{
        background: $color-cyan;
      }
      &:after{
        color: $color-cyan;
      }
    }/*特殊的span样式*/
  }/*头部导航*/
}
</style>