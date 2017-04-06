<template>
  <main-layout>
    <div id="notices">
      <headers></headers>
      <div class="content_box">
        <h1>{{title}}</h1>
        <p class="date">{{date}}</p>
        <p class="notices_txt">{{text}}</p>
      </div>
    </div>
  </main-layout>
</template>
<script>
import MainLayout from '../layouts/Main'//引用主页面
import Headers from '../components/Resume_header'//引用头部
export default {
  data: function(){
    return{
        title: '卓越英才学院开学啦',
        text: '1开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了',
        date: '发布时间: '+'2015-08-00'
    }
  },
  components: {
    MainLayout,
    Headers
  },
  methods: {
    onClick: function(){
      console.log(this);
    }
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
html{ font-size: 62.5%;}
#notices{
  .content_box{
    padding: 3% 5%;
    h1{
      font-size: 3rem;
      font-weight: bold;
      color: $color-blue;
    }
    .notices_txt{
      font-size: 1.6rem;
      color: $color-blue;
      font-weight: 700;
      line-height: 1.8rem;
    }
    .date{
      margin: 5% 0 7%;
      color: $color-gray;
      letter-spacing: 0;
      font-size: 1.5rem;
    }
  }
}
</style>