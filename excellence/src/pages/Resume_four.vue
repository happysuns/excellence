<template>
  <main-layout>
    <div id="Resume_four">
      <headers></headers>
      <navs v-bind:index="num"></navs>
      <main>
        <h1>你的性格偏向于那种?</h1>
        <div class="radio_box" v-for="(item,index) in Personalitys">
          <span class="radio_round" :class="{'radio_s':item.radio_flag}"></span>
          <input type="radio" v-show v-bind:id="item.id" v-bind:value="item.text" name="Personalitys" v-model="Personality"/>
          <label @click="radio(item,index,Personalitys)" v-bind:for="item.id">{{item.text}}</label>
        </div>
        <h1>喜欢哪些行业或领域?</h1>
        <div class="certificate_box">
          <textarea class="certificate" v-model="field" placeholder="行业领域 "></textarea>
          <button class="certificate_ok">添加</button>
          <button class="certificate_del" @click="delField">删除</button>
        </div>
        <h1>偏向于进入哪类企业?</h1>
        <div class="radio_box" v-for="(item,index) in enterprises">
          <span class="radio_round" :class="{'radio_s':item.radio_flag}"></span>
          <input type="radio" v-show v-bind:id="item.id" v-bind:value="item.text" name="enterprises" v-model="enterprise"/>
          <label @click="radio(item,index,enterprises)" v-bind:for="item.id">{{item.text}}</label>
        </div>
        <h1>倾向于从事哪类岗位?</h1>
        <div class="radios" v-for="(item,index) in postIndustrys">
          <div class="radio_box">
            <span class="radio_round" :class="{'radio_s':item.radio_flag}"></span>
            <input type="radio" v-show v-bind:id="item.id" v-bind:value="item.text" name="postIndustrys" v-model="postIndustry"/>
            <label @click="radio(item,index,postIndustrys)" v-bind:for="item.id">{{item.text}}</label>
          </div>
          <p>{{item.txt_o}}</p>
          <p>{{item.txt_t}}</p>
        </div>
        <h1>选择工作你最看重哪些点？(可多选)</h1>
        <div class="radio_box" v-for="(item,index) in focus">
          <span class="checkbox_round" :class="{'checkbox_s':item.radio_flag}"></span>
          <input class="discipline" type="checkbox" v-show v-bind:id="item.id" v-bind:value="item.text" name="focus" v-model="item.focu"/>
          <label @click="checkbox(item,index,focus)" v-bind:for="item.id">{{item.text}}</label>
        </div>
        <h1>你的兴趣爱好是什么?</h1>
        <div class="certificate_box">
          <textarea class="certificate" v-model="Interests" placeholder="兴趣爱好 "></textarea>
          <button class="certificate_ok">添加</button>
          <button class="certificate_del" @click="deleInter">删除</button>
        </div>
        <button class="certificate_ok main_ok">保存</button>
        <v-link href="/Home">
          <button class="certificate_del main_del">大功告成</button>
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
      num: '4',//传递导航index
      Personality : '',//性格倾向data 
      field: '',//喜欢行业领域data
      enterprise: '',//偏向于企业data
      postIndustry: '',//倾向于从事岗位data
      Interests: '',//兴趣爱好data
      focus: [
      { text: '基本工资' ,
        focu: '',
        id: 'focus_1'
      },
      { text: '绩效工资',
        focu: '',
        id: 'focus_2'
      },
      { text: '福利待遇',
        focu: '',
        id: 'focus_3'
      },
      { text: '休假制度',
        focu: '',
        id: 'focus_4'
      },
      { text: '工作时间',
        focu: '',
        id: 'focus_5'
      },
      { text: '工作环境',
        focu: '',
        id: 'focus_6'
      },
      { text: '人际关系 ',
        focu: '',
        id: 'focus_7'
      },
      { text: '晋升速度',
        focu: '',
        id: 'focus_8'
      },
      { text: '学习成长',
        focu: '',
        id: 'focus_9'
      },
      { text: '自由挑战',
        focu: '',
        id: 'focus_10'
      },
      { text: '舒适稳定',
        focu: '',
        id: 'focus_11'
      },
      { text: '公司规模',
        focu: '',
        id: 'focus_12'
      },
      { text: '兴趣爱好',
        focu: '',
        id: 'focus_13'
      },
      { text: '户口指标',
        focu: '',
        id: 'focus_14'
      },
      { text: '资源机会',
        focu: '',
        id: 'focus_15'
      }
      ],
      Personalitys: [
      { text: '完美型/分析型',
        id: 'Personalitys_1'
      },
      { text: '力量型/支配型',
        id: 'Personalitys_2'
      },
      { text: '活泼型/表达型',
        id: 'Personalitys_3'
      },
      { text: '和平型/和爱型',
        id: 'Personalitys_4'
      }
      ],
      enterprises: [
      { text: '国企(含国家机关及事业单位)',
        id: 'enterprises_1'
      },
      { text: '外企',
        id: 'enterprises_2'
      },
      { text: '私企',
        id: 'enterprises_3'
      },
      { text: '其他',
        id: 'enterprises_4'
      }],
      postIndustrys: [
      { text: '管理/综合',
        txt_o: '大局思维，逻辑思考',
        txt_t: '文案写作，管理能力',
        id: 'postIndustrys_1'
      },
      { text: '产品/技术',
        txt_o: '踏实肯干，数据分析',
        txt_t: '专业技能，执行能力',
        id: 'postIndustrys_2'
      },
      { text: '市场/销售',
        txt_o: '思维活跃，沟通洗脑',
        txt_t: '机会铭感，抗压能力',
        id: 'postIndustrys_3'
      }]
    }
  },
  components: {
    VLink,
    Headers,
    Navs,
    MainLayout
  },
  methods: {
    //删除行业领域
    delField(){
      this.field = '';
    },
    //删除兴趣爱好
    deleInter(){
      this.Interests = '';
    },
    /*判断点击样式 item = 类似jq value；index = 牵引；data函数的数据*/
    radio(item,index,data){
      if(typeof item.radio_flag == "undefined"){
        //遍历数组把选项全部变false
        data.forEach(function(value,index){
          value.radio_flag = false;
        });
        //在传过来的data中添加
        this.$set(item,"radio_flag",true);
      }else{
        data.forEach(function(value,index){
          value.radio_flag = false;
        });
        item.radio_flag = !item.radio_flag;
      }
    },
    checkbox(item,index,data){
      if(typeof item.radio_flag == "undefined"){
        //在传过来的data中添加
        this.$set(item,"radio_flag",true);
      }else{
        item.radio_flag = !item.radio_flag;
      }
    }
  }
}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Resume_four{
  main{
    $border: .2rem solid $color-gray;
    %box{
      display: block;
      margin: 2% auto;
    }/*盒子样式*/
    padding: 5% 7%;
    h1{
      margin: 3% 0;
      font-size: 1.7rem;
      font-weight: 700;
      color: $color-blue;
    }/*所有的标题*/
    .radio_box{
      display: -webkit-flex;
      display: -webkit-box;
      display: flex;
      align-items: center;
      margin: 4% 0;
      padding-left: 5%;
      @extend %font;/*引用字体样式*/
      @extend %box;/*引用字体样式*/
      color: $color-gray_s;
      .radio_round{
        width: 10%;
        height: 1.5rem;
        background: url(../assets/radio.png) 0 0/contain no-repeat;
      }/*按钮未点击*/
      .radio_s{
        background: url(../assets/radios.png) 0 0/contain no-repeat;
      }/*按钮点击*/
      .checkbox_round{
        width: 10%;
        height: 1.5rem;
        background: url(../assets/checkbox.png) 0 0/contain no-repeat;
      }/*按钮未点击*/
      .checkbox_s{
        background: url(../assets/checkboxs.png) 0 0/contain no-repeat;
      }/*按钮点击*/
      label{
        flex: 1;
      }
    }/*单选框盒子*/
    .radios{
      p{
        margin-left: 11%;
        font-size: 1.3rem;
        @extend %font;/*引用字体样式*/
        color: $color-gray_s;
      }
    }
    .three_course{
      .course{
        @extend %box;/*引用字体样式*/
        border:  $border;
      }
    }/*课程盒子*/
    .certificate_box,
    .training_box,
    .skills_box{
      .course{
        @extend %box;/*引用字体样式*/
        border:  $border;
      }
      .certificate{
        width: 90%;
        padding: 2% 3%;
        margin: 2% auto;
        color: $color-cyan;
        border: none;
        outline: none;
        border-bottom:  $border;
        @extend %font;/*引用字体样式*/
        @extend %box;/*引用字体样式*/
        line-height: 1.8rem;
        border:  $border;
      }/*证书*/
    }/*证书盒子*/
    .certificate_ok,
    .certificate_del{
      @extend %button;/*引用字体样式*/
    }/*按钮样式*/
    .main_ok,
    .main_del{
      margin-top: 5%;
      color: $color-gray_s;
      border: solid .2rem $color-gray_s;
    }/*跳转的按钮*/
  }
}
</style>