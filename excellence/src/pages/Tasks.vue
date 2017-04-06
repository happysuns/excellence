<!-- 第一个表单 -->
<template>
  <main-layout>
    <div id="Tasks">
      <headers :title="title"></headers>
      <v-link class="tasks_box" href="/Tasks_o" v-for="item in info">
        <span class="line cyan" :class="item.line_back"></span>
        <div class="study_box">
          <h1 class="title">{{item.title}}</h1>
          <p class="title_s">{{item.title_s}}</p>
        </div>
        <span class="flag" :class="{ 'flag-not' : !item.flag}">{{item.flag ? '已完成' : '未完成'}}</span>
        <span class="arrow">&gt;</span>
      </v-link>
    </div>
  </main-layout>
</template>
<script>
import MainLayout from '../layouts/Main.vue'//引用主页面
import VLink from '../components/VLink'//引用跳转
import Headers from '../components/Resume_header'//引用头部
export default {
  data: function(){
    return{
      title: '英才任务列表',
      info: [{
        title: '大学生职业规划培养课件1',
        flag: false,
        title_s: '任务标题',
        line_back: ''
      },
      {
        title: '大学生职业规划培养课件2',
        flag: true,
        title_s: '任务标题',
        line_back: 'sky-blue'
      },
      {
        title: '大学生职业规划培养课件3',
        flag: true,
        title_s: '任务标题',
        line_back: ''
      },
      {
        title: '大学生职业规划培养课件4',
        flag: true,
        title_s: '任务标题',
        line_back: ''
      },
      {
        title: '大学生职业规划培养课件5',
        flag: true,
        title_s: '任务标题',
        line_back: ''
      },
      {
        title: '大学生职业规划培养课件6',
        flag: true,
        title_s: '任务标题',
        line_back: 'sky-blue'
      },
      {
        title: '大学生职业规划培养课件7',
        flag: true,
        title_s: '任务标题',
        line_back: ''
      },
      {
        title: '大学生职业规划培养课件8',
        flag: true,
        title_s: '任务标题',
        line_back: 'purple'
      },]
    }
  },
  components: {
    VLink,
    Headers,
    MainLayout
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Tasks{
  .tasks_box{
    height: 23vw;
    display: -webkit-flex;
    display: -webkit-box;
    display: flex;
    border-bottom: .1rem solid $color-gray;
    overflow: hidden;
    background: $color-white;
    .line{
      display: inline-block;
      height: 100%;
      width: 4%;
    }/*左边的颜色块*/
    .cyan{ background: $color-cyan; }/*青色*/
    .purple{ background: $color-purple; }/*紫色*/
    .sky-blue{ background: $color-sky-blue; }/*天蓝色*/
    .study_img{
      width: 5rem;
      height: 5rem;
    }/*课件图片*/
    .study_box{
      flex: 1;
      padding: 6% 2.5%;
      .title{
        font-size: 1.8rem;
        font-weight: 700;
        color: $color-blue;
      }/*课件名*/
      .title_s{
        margin-top: 2%;
        font-size: 1.3rem;
        font-weight: 700;
        color: $color-blue;
      }/*任务标题*/
    }/*信息盒子*/
    .arrow{
      display: -webkit-flex;
      display: -webkit-box;
      display: flex;
      margin-right: 3%;
      align-items: center;
      font-size: 2.5rem;
      color: $color-gray;
    }/*箭头*/
    .flag{
      @extend .arrow;
      font-size: 1.5rem;
      font-weight: 700;
    }/*完成的样式*/
    .flag-not{
      color: $color-red;
    }/*未完成的样式*/
  }/*课件盒子*/
  
}
</style>