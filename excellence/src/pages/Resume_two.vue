<template>
  <main-layout>
    <div id="Resume_two">
      <headers></headers>
      <navs v-bind:index="num"></navs>
      <main>
        <h1>目前就读的学校(全称)</h1>
        <input class="school" v-model="school" placeholder="学校">
        <h1>学科类别</h1>
        <div class="radio_box" v-for="(item,index) in discip">
          <span class="radio_round" :class="{'radio_s':item.radio_flag}"></span>
          <input type="radio" v-show v-bind:id="item.id" v-bind:value="item.text" name="discip" v-model="picked"/>
          <label @click="radio(item,index,discip)" v-bind:for="item.id">{{item.text}}</label>
        </div>
        <h1>所学专业</h1>
        <input class="school" v-model="professional" placeholder="所学专业">
        <h1>即将取得的学位</h1>
        <div class="radio_box" v-for="(item,index) in degrees">
          <span class="radio_round" :class="{'radio_s':item.radio_flag}"></span>
          <input type="radio" v-show v-bind:id="item.id" v-bind:value="item.text" name="degrees" v-model="degree"/>
          <label @click="radio(item,index,degrees)" v-bind:for="item.id">{{item.text}}</label>
        </div>
        <h1>年级最好排名</h1>
        <div class="radio_box" v-for="(item,index) in Best_ranking">
          <span class="radio_round" :class="{'radio_s':item.radio_flag}"></span>
          <input type="radio" v-show v-bind:id="item.id" v-bind:value="item.text" name="Best_ranking" v-model="Best_r"/>
          <label @click="radio(item,index,Best_ranking)" v-bind:for="item.id">{{item.text}}</label>
        </div>
        <h1>列举所学最好的三门课程</h1>
        <div class="three_course" v-for="item in course">
          <input class="school course" v-model="item.course" placeholder="课程名称">
        </div>
        <h1>曾或得过的资格证书</h1>
        <div class="certificate_box">
          <textarea class="school certificate" v-model="certificate" placeholder="证书名称 "></textarea>
          <button class="certificate_ok">添加</button>
          <button class="certificate_del" @click="deleCerti">删除</button>
        </div>
        <h1>曾接受过的培训</h1>
        <div class="training_box">
          <textarea class="school certificate" v-model="training" placeholder="培训名称 "></textarea>
          <button class="certificate_ok">添加</button>
          <button class="certificate_del" @click="deleTrain">删除</button>
        </div>
        <h1>技能或特长</h1>
        <div class="skills_box">
          <input class="school course" v-model="skills" placeholder="课程名称">
          <textarea class="school certificate" v-model="skills_t" placeholder="技能或特长所达到的水平描述(限50字内) "></textarea>
          <button class="certificate_ok">添加</button>
          <button class="certificate_del" @click="deleSkill">删除</button>
        </div>
        <button class="certificate_ok main_ok">保存</button>
        <v-link href="/Resume_three">
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
      num: '2',//传递导航index
      school: '',//学校data
      picked: '',//学科类别data
      professional: '',//所学专业data
      degree: '',//取得学位data
      Best_r: '',//全年级最好data
      certificate: '',//曾获得的资格证书data
      training: '',//曾接受过的培训data
      skills: '',//技能或特长data
      skills_t: '',//技能或特长(描述)data
      discip: [
      { text: '哲学' ,
        id: 'discip_1'
      },
      { text: '经济学',
        id: 'discip_2'
      },
      { text: '法学',
        id: 'discip_3'
      },
      { text: '教育学',
        id: 'discip_4'
      },
      { text: '文学',
        id: 'discip_5'
      },
      { text: '历史学',
        id: 'discip_6'
      },
      { text: '理学 ',
        id: 'discip_7'
      },
      { text: '工学',
        id: 'discip_8'
      },
      { text: '农学',
        id: 'discip_9'
      },
      { text: '医学',
        id: 'discip_10'
      },
      { text: '军事学',
        id: 'discip_11'
      },
      { text: '管理学',
        id: 'discip_12'
      },
      { text: '艺术学',
        id: 'discip_13'
      }
      ],
      degrees: [
      { text: '学士',
        id: 'degree_1',
      },
      { text: '硕士',
        id: 'degree_2',
      },
      { text: '博士',
        id: 'degree_3',
      }
      ],
      Best_ranking: [
      { text: '前5%',
        id: 'best_1'
      },
      { text: '6%-20%',
        id: 'best_2'
      },
      { text: '21%-50%',
        id: 'best_3'
      },
      { text: '50%以后',
        id: 'best_4'
        }
      ],
      course: [
      { course: '' },
      { course: '' },
      { course: '' }
      ]/*最好三门课程data*/
    }
  },
  components: {
    VLink,
    Headers,
    Navs,
    MainLayout
  },
  methods:{
    //删除资格证书
    deleCerti(){
      this.certificate = '';
    },
    //删除受过的培训
    deleTrain(){
      this.training = '';
    },
    deleSkill(){
      this.skills = '';
      this.skills_t = '';
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
    }
  },

}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
#Resume_two{
  overflow: hidden;
  main{
    $border: .2rem solid $color-gray;
    %font{
      font-size: 1.7rem;
      font-weight: 700;
    }/*字体样式*/
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
    .school{
      width: 90%;
      padding: 2% 3%;
      margin: 2% 0;
      @extend %font;/*引用字体样式*/
      color: $color-cyan;
      border: none;
      outline: none;
      border-bottom:  $border;
    }/*学校输入框*/
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
      label{
        flex: 1;
      }
    }/*单选框盒子*/
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
        @extend %font;/*引用字体样式*/
        @extend %box;/*引用字体样式*/
        line-height: 1.8rem;
        padding: 5% 3%;
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