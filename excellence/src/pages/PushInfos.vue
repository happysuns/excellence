<template>
  <main-layout>
    <div id="PushInfos">
      <headers></headers>
      <main v-for="item in items">
        <h1 class="title">{{item.title}}</h1>
        <span class="date">{{item.date}}</span>
        <span class="address">{{item.address}}</span>
        <h2 class="t_title">{{item.t_title}}</h2>
        <p class="notice_txt">{{item.text}}</p>
      </main>
    </div>
  </main-layout>
</template>
<script>
import MainLayout from '../layouts/Main.vue'//引用主页面
import Headers from '../components/Resume_header'//引用头部
export default {
  data: function(){
    return{
      items:[{
        title: '实习生',
        t_title: '[岗位职责]',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了',
        date: '发布时间: '+'2016-08-08',
        address: '工作地点: '+'北京'
      }]
    }
  },
  components: {
    Headers,
    MainLayout
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#PushInfos{
  overflow: hidden;
  header{
    padding: 3%;
    overflow: hidden;
    background: $color-blue;
    img{
      width: 10%;
      height: auto;
    }/*logo*/
  }/*头部*/
  main{
    padding: 2% 3%;
    border-bottom: .1rem solid   $color-gray;
    .title{
      margin: 3% 0;
      font-size: 2.5rem;
      font-weight: 700;
      color: $color-wathet;
    }/*标题*/
    .t_title,
    .notice_txt{
      font-size: 1.8rem;
      font-weight: 700;
      color: $color-wathet;
    }
    .date,
    .address{
      display: inline-block;
      margin: 2% 0;
      font-size: 1.3rem;
    }
    .t_title{
      margin: 4% 0;
    }/*职责*/
    .date{
      color:  $color-gray;
    }/*日期*/
    .address{
      float: right;
      color: $color-cyan;
      @include clearfix;
    }/*地点*/
  }/*右边信息盒子*/
}
</style>