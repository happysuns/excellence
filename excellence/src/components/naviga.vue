<template>
  <div class="naviga">
    <ul>
      <v-link v-for="item in items" v-bind:href="item.href">
          <span class="value">{{item.value}}<span class="state">{{item.state}}</span></span>
      </v-link>
    </ul>
    <div class="naviga_b"><v-link :href="push_href" v-html="push"></v-link><v-link :href="course_href" v-text="course"></v-link><v-link :href="notice_href" v-text="notice"></v-link></div>
  </div>
</template>

<script>
import VLink from '../components/VLink'//引用跳转

export default {
  name: 'naviga',
  data () {
    return {
      items: [{
        value: '75%',
        state: '简历完成度',
        img: '../static/m_r.png',
        href: '/Resume_one'
      },
      {
        value: '5',
        state: '签到次数',
        img: '../static/m_s.png',
        href: '/SignIn'
      },
      {
        value: '8/15',
        state: '任务完成数',
        img: '../static/m_t.png',
        href: '/Tasks'
      },
      {
        value: '180',
        state: '在线得分',
        img: '../static/m_sc.png',
        href: '/Score'
      }],
      push: '卓越英才内推信息',
      push_href: '/PushInfo',
      course: '课程学习',
      course_href: '/Course',
      notice: '通知',
      notice_href: '/Notice'
    }
  },
  components: {
    VLink
  }
}
</script>

<style lang="scss">

$color-yell: rgba(255,181,64,1); //黄色
$color-cyan:  rgba(32,191,175,1); //青色
$color-purple: rgba(103,103,153,1); //紫色
$color-blue: rgba(70,175,224,1); //蓝色
%font-s{
  font-size: 1.5rem;
  font-weight: 700;
  color: #fff;
}/*共有文字*/
%style-b{
  display: flex;
  display: -webkit-flex;
  display: webkit-box;
  box-sizing: border-box;
  align-content: flex-start;
  border-radius: .3rem;
  box-shadow: 0 0 .5rem rgba(0,0,0,.5);
}
.naviga{
  ul{
    margin: 0 auto;
    padding: 0 3%;
    *zoom: 1;
    &:before,
    &:after {
      display: table;
      content: "";
    }
    &:after {
      clear: both;
    }
    a{
      float: left;
      width: 45%;
      margin: 2%;
      padding: 3% 5%;
      @extend %style-b;/*引用盒子样式*/
      &:first-child{
        background: $color-blue url('../../static/m_r.png') 0 0/22% no-repeat;
        background-position: 90% center;
      }
      &:nth-child(2){
        background: $color-yell url('../../static/m_s.png') 0 0/22% no-repeat;
        background-position: 90% center;
      }
      &:nth-child(3){
        background: $color-purple url('../../static/m_t.png') 0 0/18% no-repeat;
        background-position: 90% center;
      }
      &:nth-child(4){
        background: $color-cyan url('../../static/m_sc.png') 0 0/18% no-repeat;
        background-position: 90% center;
      }
      .value{
        flex: 1;
        margin-left: -40%;
        text-align: center;
        @extend %font-s;/*引用文字样式*/
        .state{
          display: block;
          margin-top: 1%;
          font-size: 1.2rem;
        }
      }/*导航左边信息*/
      .nav_img{
        display: inline-block;
        width: 1px;
        height: 1px;
      }/*右边图片*/
    }/*li结束标签*/
  }/*ul结束标签*/
  .naviga_b{
    @extend %style-b;/*引用盒子样式*/
    margin: 3% 5%;
    width: 88%;
    a{
      padding: 6% 1%;
      flex: 1;
      @extend %font-s;/*引用文字样式*/
      font-size: 1.2rem;
      &:first-child{
        flex: 1.5;
        padding-left: 12%;
        background: $color-blue url('../../static/m_p.png') 0 0/10% no-repeat;
        background-position: 10% center;
      }
      &:nth-child(3){
        text-align: center;
        background: $color-yell;
      }
      &:nth-child(2){
        text-align: center;
        background: $color-purple;
      }
    }
  }
}

</style>
