<template>
  <main-layout>
    <div id="Resume_three">
      <headers></headers>
      <navs v-bind:index="num"></navs>
      <main>
        <div class="form_box" v-for="item in form">
          <h1>{{item.title}}</h1>
          <textarea class="title_input" v-model="item.data" v-if="item.flage" v-bind:placeholder="item.text "></textarea>
          <textarea class="details_input" v-model="item.data_t" v-bind:placeholder="item.text_t"></textarea>
          <button class="certificate_ok">添加</button>
          <button class="certificate_del" @click="data_t(item)">删除</button>
        </div>
        <button class="certificate_ok main_ok">保存</button>
        <v-link href="/Resume_four">
          <button class="certificate_del main_del">下一步</button>
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
document.body.scrollTop = 0;
export default {
  data: function(){
    return{
      num: '3',
      form: [{
        flage: true,
        title: '奖学金/学术论文/其他荣誉',
        data: '',
        text: '奖学金/学术论文/其他荣誉',
        data_t: '',
        text_t: '含金量/重要性描述(限50字内)'
      },
      {
        flage: true,
        title: '社团经历/校内实践/项目经验',
        data: '',
        text: '社团名称及职务/校内实践/项目经验',
        data_t: '',
        text_t: '案例成果(你所做的事情及达到的效果限100字内)'
      },
      {
        flage: true,
        title: '校外实习/校外实践/创业经历',
        data: '',
        text: '实习公司及职务/实践项目名称/创业项目名称',
        data_t: '',
        text_t: '案例成果(你所做的事情及达到的效果限100字内)'
      },
      {
        flage: false,
        title: '人生顿悟/特殊经历',
        data_t: '',
        text_t: '过程描述(限100字内)'
      } ]
      
    }
  },
  components: {
    VLink,
    Headers,
    Navs,
    MainLayout
  },
  methods: {
    data_t(item){
      item.data = '';
      item.data_t = '';
    }
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Resume_three{
  main{
    padding: 5% 7%;
    .form_box{
      margin: 8% 0;
      h1{
        margin: 3% 0;
        font-size: 1.7rem;
        font-weight: 700;
        color: $color-blue;
      }/*所有的标题*/
      .title_input,
      .details_input{
        width: 90%;
        padding: 4% 3%;
        margin: 2% 0;
        line-height: 1.8rem;
        @extend %font;/*引用字体样式*/
        color: $color-cyan;
        border: none;
        outline: none;
        display: block;
        margin: 2% auto;
        border:  .2rem solid $color-gray;
      }
      .details_input{
        height: 8rem;
      }
    }
    .certificate_ok,
    .certificate_del{
      @extend %button;/*引用字体样式*/
    }/*按钮样式*/
    .main_ok,
    .main_del{
      margin-top: 5%;
      color: $color-gray_s;
      border: solid .2rem $color-gray_s;
    }/*确认整页按钮*/
  }
}
</style>