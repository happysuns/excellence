<!-- 第一个表单 -->
<template>
  <div id="Task">
  <span class="tas_title">英才任务列表</span>
    <headers></headers>
      <article>
        <h1 class="task_title">实践任务</h1>
        <span class="title_one">任务1</span>
        <h1 class="title_text">根据行企课程的内容，选择一个你喜欢的行业，进行行业分析</h1>
        <p class="task_tips">任务思路，必须根据自己实际情况做出回答，可先说自己的优点，结合岗位胜任力作答</p>
        <button class="task_file">选择文档附件</button><button class="task_file_ok">点击上传</button>
        <p class="task_tips_t">附件大小不超过5MB</p>
      </article>
      <button class="task_ok">提交任务</button>
  </div>
</template>
<script>
import VLink from '../components/VLink'//引用跳转
import Headers from '../components/Resume_header'//引用头部
export default {
  data: function(){
    return{
      info: [{
        img: './static/1.jpg',
        title: '大学生职业规划培养课件',
        size: '1.45'
      }]
    }
  },
  components: {
    VLink,
    Headers
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Task{
  .tas_title{
    position: absolute;
    top: 4%;
    right: 7%;
    font-size: 1.5rem;
    font-weight: 700;
    color: $color-white;
  }
  article{
    padding: 4% 5%;
    color: $color-blue;
    .task_title{
      margin: 3% 0;
      font-size: 1.6rem;
      font-weight: 700;
    }/*实践任务*/
    .title_one{
      position: absolute;
      font-size: 1.6rem;
    }/*任务1*/
    .title_text{
      margin: 3% 0 3% 15%;
      font-size: 1.5rem;
    }/*任务内容*/
    .task_tips{
      margin: 5% 0;
      font-size: 1.0rem;
      color: $color-gray_s;
    }/*任务思路*/
    .task_file{
      width: 70%;
      padding: 2% 5%;
      margin-right: 2%;
      font-size: 1.6rem;
      font-weight: 700;
      color: $color-blue;
      background: $color-white;
      border: .1rem solid $color-blue;
    }/*选择文档附件*/
    .task_file_ok{
      font-size: 1.4rem;
      color: $color-red;
      background: $color-white;
    }
    .task_tips_t{
      @extend .task_tips;/*引用任务思路的样式*/
    }
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