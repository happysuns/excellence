<!-- 第一个表单 -->
<template>
  <main-layout>
    <div id="Courses">
      <headers></headers>
      <div class="course_box" href="Courses" v-for="item in info">
        <div class="study_box">
          <h1 class="title"><span>{{item.title}}</span></h1>
          <p class="size">发布时间: <span>{{item.size}}</span></p>
          <p class="conter">{{item.text}}</p>
        </div>
        <button class="music_box" @click="musicBtn">
          <img class="study_img" v-bind:src="item.img">
        </button>
        <span class="cou_down">课程录音点击播放</span>
        <audio id="music" class="play" v-show src="../../static/Summer.mp3">
        您的浏览器不支持 audio 标签。
        </audio>
      </div>
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
      info: [{
        img: './static/music.png',
        title: '大学生职业规划培养课件',
        size: '2016-8-8',
        text: '卓越因材学院开学啦,卓越因材学院开学啦,卓越因材学院开学啦,卓越因材学院开学啦,卓越因材学院开学啦,卓越因材学院开学啦,卓越因材学院开学啦卓越因材学院开学啦卓越因材学院开学啦卓越因材学院开学啦卓越因材学院开学啦'
      }]
    }
  },
  components: {
    VLink,
    Headers,
    MainLayout
  },
  methods: {
    musicBtn: function(){
      var audio = document.getElementById('music');
      if (audio.className == "play") {
          audio.className = ' ';
          audio.play();//开始播放
      } else {
          audio.className = 'play';
          audio.pause();//暂停播放
      }
    }
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Courses{
  height: 100%;
  background: $color-white;
  .course_box{
    display: -webkit-flex;
    display: -webkit-box;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 5% 4%;
    .music_box{
      background: transparent;
      border: none;
      outline: none;
      .study_img{
        width: 4rem;
        height: 4rem;
        margin: 1% auto;
      }/*课件图片*/
    }//课件按钮
    .study_box{
      padding: 3%;
      .title{
        @extend %font;
        font-size: 2.4rem;
        color: $color-blue;
      }/*课件名*/
      .size{
        margin-top: 2%;
        font-size: 1.0rem;
      }/*时间大小*/
    }/*信息盒子*/
  }/*课件盒子*/
  .cou_down{
    font-size: 1.6rem;
    font-weight: 700;
    color: $color-gray;
    text-align: center;
  }/*播放按钮*/
  .conter{
    margin: 5% 0;
    font-size: 1.8rem;
    font-weight: 550;
    color: $color-wathet;
  }/*内容的样式*/
}
</style>