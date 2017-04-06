<template>
  <main-layout>
    <div id="PushInfos">
      <headers :title="title"></headers>
      <p class="push_tips">怎样从校园小白晋升职场英雄？<v-link href="/Notices"><span>点击查看得分规则</span></v-link></p>
      <main>
        <div class="push_top">
          <figure v-for="top in tops">
            <img v-bind:class="{top_one: top.flag}" v-bind:src="top.src">
            <figcaption class="top">{{top.top}}</figcaption>
            <p class="name">{{top.name}}</p>
            <p class="info">{{top.info}}</p>
          </figure>
        </div>
        <article v-for="item in items">
          <span class="num">{{item.num}}</span>
          <img class="m_img" v-bind:src="item.img">
          <div class="info_box">
            <h1 class="name">{{item.name}}</h1>
            <p class="notice_txt">{{item.text}}</p>
          </div>
          <span class="dig">{{item.dig}}</span>
        </article>
      </main>
    </div>
  </main-layout>
</template>
<script>
import MainLayout from '../layouts/Main.vue'//引用主页面
import Headers from '../components/Resume_header'//引用头部
import VLink from '../components/VLink'//引用跳转
export default {
  data: function(){
    return{
      title: '英才联盟排行榜',
      tops:[{
        src: '../static/1.jpg',
        top: '#3',
        name: '张三',
        info: '232'
      },
      {
        src: '../static/1.jpg',
        top: '#1',
        flag: 'true',
        name: '张三',
        info: '232'
      },
      {
        src: '../static/1.jpg',
        top: '#2',
        name: '张三',
        info: '232'
      }],
      items:[{
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了开学了开学了了开学了开学了了开学了开学了了开学了开学了了了',
        dig: '800'
      },
      {
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了了',
        dig: '800'
      },
      {
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了了',
        dig: '800'
      },
      {
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了了',
        dig: '800'
      },
      {
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了了',
        dig: '800'
      },
      {
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了了',
        dig: '800'
      },
      {
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了了',
        dig: '800'
      },
      {
        num: '#4',
        img: '../static/1.jpg',
        name: '吴一凡',
        text: '开学了开学了了',
        dig: '800'
      }]
    }
  },
  components: {
    Headers,
    MainLayout,
    VLink
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
body{
  background: $color-gray_t;
}
#PushInfos{
  overflow: hidden;
  .push_tips{
    margin: 3% 0;
    padding: 0 5%;
    font-size: 1.3rem;
    color: $color-wathet;
    span{
      color: $color-cyan;
    }
  }/*提示部分*/
  main{
    margin: 1% 3%;
    border-radius: .4rem;
    box-shadow: 0 0 .5rem rgba(0,0,0,.2);
    background: $color-white;
    .push_top{
      display: -webkit-box;
      display: -webkit-flex;
      display: flex;
      width: 100%;
      padding: 3% 0;
      figure{
        width: 33%;
        flex: 1;
        text-align: center;
        padding-top: 5%;
        img{
          width: 65%;
          height: auto;
          margin: 0 auto;
          border-radius: .3rem;
          box-shadow: 0 0 .5rem rgba(0,0,0,.5);
        }/*头像*/
        .top_one{
          width: 75%;
          margin-top: -10%;
        }/*第一名的头像样式*/
        .top{
          margin: 2% 0;
          font-size: 1.0rem;
          color: $color-gray;
        }/*名次*/
        .name{
          font-size: 2rem;
          font-weight: 700;
          color: $color-wathet;
        }/*姓名*/
        .info{
          @extend .top;//引用top的样式
          font-size: 1.2rem;
        }
      }/*图片盒子*/
    }/*top123*/
  }/*content盒子*/
  article{
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    border-top: .1rem solid  $color-gray;
    padding: 4% 3%;
    .num{
      flex: .5;
      line-height: 3.5rem;
      vertical-align: middle;
      font-size: 1.8rem;
      font-weight: 700;
      color: $color-gray_s;
    }/*名次*/
    .m_img{
      flex: .5;
      margin-right: 4%;
      width: auto;
      height: 3.8rem;
      border-radius: .3rem;
    }/*头像*/
    .info_box{
      flex: 2;
      margin-right: 8%;
      .name{
        font-size: 1.3rem;
        font-weight: 700;
        color: $color-gray_s;
      }/*姓名*/
      .notice_txt{
        margin-top: 5%;
        @include ellipsis(1);/*强制一行*/
        font-size: 1.0rem;
        color: $color-gray;
      }/*描述*/
    }/*姓名跟描述盒子*/
    .dig{
     @extend .num;
     font-size: 2.5rem;
    }/*积分数*/
  }/*右边信息盒子*/
}
</style>