<!-- 第一个表单 -->
<template>
<main-layout>
  <div id="Resume_one">
    <headers></headers>
    <navs v-bind:index="num"></navs>
    <main>
      <img class="header_img" src="../../static/1.jpg">
      <div class="input_box" v-for="item in info">
        <label v-bind:class="{special_lab: item.lable_flag}">{{item.title}}</label>
        <input v-bind:class="{special_inp: item.input_flag , specials_inp:item.inputs_flag}" v-model="item.data" placeholder="">
      </div>
      <button class="main_ok">保存</button>
      <v-link href="/Resume_two">
        <button class="main_del">下一步</button>
      </v-link>
    </main>
  </div>
</main-layout>
</template>
<script>
import MainLayout from '../layouts/Main.vue'//引用主页面
import VLink from '../components/VLink'//引用跳转
import Headers from '../components/Resume_header'//引用头部
import Navs from '../components/Resume_nav'//引用导航
export default {
  data: function(){
    return{
      num: '1',//传递导航index
      info: [{
        inputs_flag: true,
        lable_flag: false,
        input_flag: false,
        title: '姓名',
        data: ''
      },
      {
        inputs_flag: true,
        lable_flag: false,
        input_flag: false,
        title: '性别',
        data: ''
      },
      {
        lable_flag: false,
        input_flag: false,
        title: '出生日期',
        data: ''
      },
      {
        lable_flag: false,
        input_flag: false,
        title: '籍贯',
        data: ''
      },
      {
        lable_flag: false,
        input_flag: false,
        title: '联系电话',
        data: ''
      },
      {
        lable_flag: true,
        input_flag: true,
        title: '常用邮箱',
        data: ''
      },
      {
        lable_flag: true,
        input_flag: true,
        title: '微信号',
        data: ''
      }]
    }
  },
  components: {
    VLink,
    Headers,
    Navs,
    MainLayout
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Resume_one{
  main{
    padding: 5% 7%;
    .header_img{
      position: absolute;
      right: 8%;;
      width: 29%;
      height: auto;
      border-radius: .5rem;
      border: .2rem solid $color-cyan;
    }/*头像图片*/
    .input_box{
      input{
        @extend %input;/*引用字体样式*/
        font-size: 1.7rem;
      }/*输入框样式*/
      label{
        @extend %font;/*引用字体样式*/
        color:  $color-gray_s;
        position: absolute;
        font-size: 1.7rem;
        margin: 1% 0 0 3%;
      }/*label的样式*/
      .special_lab{
        position: static;
      }/*设置不一样的label样式*/
      .special_inp{
        text-align: left;
        padding-left: 3%;
        width: 92%;
      }/*设置不一样的input样式*/
      .specials_inp{
        width: 30%;
        margin: 6% 0;
      }/*姓名性别的input*/
    }/*输入框盒子*/
    .main_ok,
    .main_del{
      @extend %button;/*引用样式*/
      margin-top: 5%;
      color: $color-blue;
      border: solid .2rem $color-blue;
    }
  }
}
</style>