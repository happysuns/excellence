<!-- 第一个表单 -->
<template>
  <main-layout>
    <div id="Task">
      <headers :title="title"></headers>
        <article>
          <h1 class="task_title">进阶任务</h1>
          <div v-for="item in info">
            <span class="title_one">{{item.title}}</span>
            <h1 class="title_text">{{item.title_text}}</h1>
            <textarea v-model="item.Personality" class="Personalitys" placeholder="限200字内"></textarea>
            <p class="task_tips">{{item.task_tips}}</p>
          </div>
          <div class="button_box">
            <button class="task_file">保存界面</button><button class="task_file_ok">提交任务</button>
          </div>
        </article>
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
        title: '任务1',
        title_text: '根据职业生涯规划课关于人格特质的讲授，说出自己的三个个性特质。',
        Personality: '',
        task_tips: '任务思路，必须根据自己实际情况做出回答，可先说自己的优点，结合岗位胜任力作答'
      },
      {
        title: '任务2',
        title_text: '根据职业生涯规划课关于人格特质的讲授，说出自己的三个个性特质。',
        Personality: '',
        task_tips: '任务思路，必须根据自己实际情况做出回答，可先说自己的优点，结合岗位胜任力作答'
      }]
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
#Task{
  background: $color-white;
  article{
    padding: 4% 5%;
    color: $color-blue;
    .task_title{
      margin: 3% 0;
      padding: 5% 0 5% 15%;
      font-size: 1.6rem;
      font-weight: 700;
      background: url('../../static/tasks.png') 0 0/11% no-repeat;
      background-position: left center;
    }/*实践任务*/
    .title_one{
      position: absolute;
      font-size: 1.6rem;
      font-weight: 700;
    }/*任务1*/
    .title_text{
      margin: 3% 0 3% 15%;
      font-size: 1.5rem;
      font-weight: 700;
    }/*任务内容*/
    .Personalitys{
      display: block;
      margin: 0 auto;
      padding: 2%;
      width: 90%;
      height: 11rem;
      border: .1rem solid $color-blue;
    }/*文本域输入*/
    .task_tips{
      margin: 5% 3%;
      font-size: 1.0rem;
      color: $color-gray_s;
    }/*任务思路*/
    .button_box{
      display: -webkit-flex;
      display: -webkit-box;
      display: flex;
      .task_file{
        flex: 1;
        padding: 2% 5%;
        margin-right: 2%;
        font-size: 1.6rem;
        font-weight: 700;
        color: $color-blue;
        background: $color-white;
        border: .1rem solid $color-blue;
      }/*保存界面*/
      .task_file_ok{
        @extend .task_file;
        color: $color-cyan;
        border: .1rem solid $color-cyan;
        background: $color-white;
      }/*提交任务*/
    }/*按钮盒子*/
  }/*内容*/
  .task_ok{
    display: block;
    margin: 10% auto 0;
    padding: 2% 0;
    width: 90%;
    text-align: center;
    font-size: 2rem;
    color: $color-cyan;
    background: $color-white;
    border: .1rem solid $color-cyan;
  }
}
</style>