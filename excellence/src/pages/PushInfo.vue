<template>
  <main-layout>
    <div id="notice">
      <headers></headers>
      <header>
        <ul id="notice_ul">
          <li :class="{active: isFinished}" v-on:click="toggleFinis">实习/招聘信息</li>
          <li :class="{active: isFinisheds}" v-on:click="toggleFin">卓越英才内推会</li>
        </ul>
      </header>
      <v-link v-for="item in items" href="/PushInfos">
        <main>
          <img class="m_img" :src="item.img">
          <div class="info_box">
            <h1 class="title">{{item.title}}</h1>
            <h2 class="t_title">{{item.t_title}}</h2>
            <p class="notice_txt">{{item.text}}</p>
            <p class="date">{{item.date}}</p>
          </div>
        </main>
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
      isFinished: true,
      isFinisheds: false,
      items:[{
        img: '../../static/1.jpg',
        title: '网易品牌推广实习生',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      },
      {
        img: '../../static/1.jpg',
        title: '网易品牌推广实习生',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      },
      {
        img: '../../static/1.jpg',
        title: '网易品牌推广实习生',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      },
      {
        img: '../../static/1.jpg',
        title: '网易品牌推广实习生',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      }]
    }
  },
  components: {
    MainLayout,
    VLink,
    Headers
  },
  methods: {
    toggleFinis:function(){
      this.isFinished = true;
      this.isFinisheds = false;
      this.items = [{
        img: '../../static/1.jpg',
        title: '网易品牌推广实习生',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      },
      {
        img: '../../static/1.jpg',
        title: '网易品牌推广实习生',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      },
      {
        img: '../../static/1.jpg',
        title: '网易品牌推广实习生',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      }]
    },
    toggleFin(){
      this.isFinisheds = true;
      this.isFinished = false;
      this.items = [{
        img: '../../static/1.jpg',
        title: '卓越因材背时大会推会',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      },
      {
        img: '../../static/1.jpg',
        title: '卓越因材背时大会推会',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      },
      {
        img: '../../static/1.jpg',
        title: '卓越因材背时大会推会',
        t_title: '[岗位职责]',
        text: '网易新闻品牌部负责网易新闻整体品牌管理和推广',
        date: '2016-08-08'
      }]
    }
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#notice{
  overflow: hidden;
  background: $color-white;
  header{
    padding: 3%;
    overflow: hidden;
    background: $color-blue;
    ul{
      @include clearfix;
      li,.active{
        position: relative;
        float: left;
        padding: 2% 0;
        width: 49%;
        text-align: center;
        font-size: 1.5rem;
        font-weight: 700;
        color:  $color-gray;
      }
      li:first-child{
        border-right: .1rem solid $color-gray;
      }
      li:last-child{
        border-left: .1rem solid $color-gray;
      }
      .active{
        &:after{
          content: '';
          position: absolute;
          bottom: -33%;
          left: 50%;
          margin-left: -1rem;
          display: inline-block;
          width: 0;
          height: 0;
          border-style: dashed dashed dashed solid;
          border-color:  transparent transparent  $color-white transparent;
          border-width: 1rem;
        }
      }
    }/*顶部导航*/
  }/*头部*/
  main{
    padding: 2% 3%;
    border-bottom: .1rem solid   $color-gray;
    .m_img{
      float: left;
      width: 4rem;
      height: 4rem;
      border-radius: .3rem;
      margin: 2% 5% 0 0;
    }/*图片*/
    .info_box{
      overflow: hidden;
      color:  $color-wathet;
      .title{
        font-size: 1.7rem;
        font-weight: 700;
        margin-bottom: 4%;
      }/*标题*/
      .t_title,
      .notice_txt,
      .date{
        font-size: 1.3rem;
      }
      .t_title{
        margin: 2% 0;
        font-weight: 700;
      }/*职责*/
      .notice_txt{
        font-weight: 700;
        @include ellipsis(1);/*强制一行*/
      }/*职责简介内容*/
      .date{
        margin: 3% 0;
        color:  $color-gray;
      }/*日期*/
    }/*右边信息盒子*/
  }/*content*/
}
</style>