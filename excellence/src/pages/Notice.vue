<template>
  <main-layout>
    <div id="notice">
      <headers></headers>
      <h1>通知</h1>
      <v-link v-for="item in items" href="/Notices">
        <h2 class="notice_title">{{item.title}}</h2>
        <p class="notice_txt">{{item.text}}</p>
        <p class="date">{{item.date}}</p>
      </v-link>
    </div>
  </main-layout>
</template>

<script>
import MainLayout from '../layouts/Main'//引用主页面
import VLink from '../components/VLink'//引用跳转
import Headers from '../components/Resume_header'//引用头部
export default {
  data: function(){
    return{
      items: [{
        title: '卓越英才开学了1!!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了1',
        date: '2016-08-08'
      },
      {
        title: '卓越英才开学了2!!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了2',
        date: '2016-08-08'
      },
      {
        title: '卓越英才开学了3!!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了3',
        date: '2016-08-08'
      },
      {
        title: '阿斯蒂芬噶士大夫4!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了4',
        date: '2016-08-08'
      },
      {
        title: '卓越英才开学了5!!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了5',
        date: '2016-08-08'
      },
      {
        title: '卓越英才开学了!!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了',
        date: '2016-08-08'
      },
      {
        title: '卓越英才开学了!!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了',
        date: '2016-08-08'
      },{
        title: '卓越英才开学了!!!!',
        text: '开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了开学了',
        date: '2016-08-08'
      }
      ]
    }
  },
  components: {
    MainLayout,
    VLink,
    Headers
  },
  methods:{
    details: function(){
      alert(this);
    }
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#notice{
  background: $color-white;
  h1{
    margin: 5% 3%;
    padding-left: 3%;
    border-bottom: .3rem solid $color-blue;
    font-size: 3.0rem;
    font-weight: bold;
    color: $color-blue;
  }/*通知*/
  a{
    display: block;
    padding: 3% 5%;
    font-weight: 700;
    line-height: 1.8rem;
    color: $color-blue;
    border-bottom: .1rem solid $color-gray;
    .notice_title{
      font-size: 1.8rem;
      font-weight: 700;
    }/*标题*/
    p{
      font-size: 1.5rem;
      margin: 2% 0;
    }/*说明*/
    .date{
      color: $color-gray;
      font-size: 1.4rem;
    }/*时间*/
  }
}
</style>