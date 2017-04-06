<!-- 第一个表单 -->
<template>
  <main-layout>
    <div id="Course">
      <headers :title="title"></headers>
      <v-link class="course_box" href="/Courses" v-for="item in info">
        <div class="study_img_b">
          <img class="study_img" v-bind:src="item.img">
        </div>
        <div class="study_box">
          <h1 class="title">{{item.title}}</h1>
          <p class="size"><span>{{item.size}}</span></p>
        </div>
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
      title: '课程学习资料列表',
      info: [{
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
      },
      {
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
      },
      {
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
      },
      {
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
      },
      {
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
      },
      {
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
      },
      {
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
      },
      {
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '2016.02.05'
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
#Course{
  background: $color-white;
  .course_box{
    display: -webkit-flex;
    display: -webkit-box;
    display: flex;
    padding: 5% 4%;
    border-bottom: .1rem solid $color-gray;
    .study_img_b{
      display: -webkit-flex;
      display: -webkit-box;
      display: flex;
      align-items: center;
      .study_img{
        width: 5rem;
        height: 5rem;
      }/*课件图片*/
    }/*课件盒子*/
    .study_box{
      flex: 1;
      padding: 3%;
      .title{
        @extend %font;
        color: $color-blue;
      }/*课件名*/
      .size{
        margin-top: 2%;
        font-size: 1.4rem;
      }/*课件大小*/
    }/*信息盒子*/
    .arrow{
      display: -webkit-flex;
      display: -webkit-box;
      display: flex;
      align-items: center;
      font-size: 2.5rem;
      color: $color-gray;
    }/*箭头*/
  }/*课件盒子*/
  
}
</style>