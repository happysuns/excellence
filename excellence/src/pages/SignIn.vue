<template>
  <main-layout>
    <div id="signin">
      <header>
      <iframe name="uploadfrm" id="uploadfrm" style="display: none;"></iframe>
      <form name="formHead" method="post" action="" id="formHead" enctype="multipart/form-data" target="uploadfrm">
         <input type="file" name="file_head" id="file_head" @click="setImage" />
      </form>
      <div id="DivUp">
          <p>你确认签到吗？</p>
          <button class="divup" @click="imgok">确认</button>
          <button class="divup" @click="imgNot">取消</button>
      </div>
        <span class="header_sign">已签到<span>{{sign_num}}</span>次</span>
        <div class="hader_box">
          <img class="header_img" src="../assets/smile.png">
          <span>微笑签到按钮</span>
        </div>
      </header>
      <div class="line"></div>
      <div class="signin_box" v-for="item in items">
        <span class="sig_seria"></span>
        <p class="date">{{item.date}}</p>
        <h1 class="address">{{item.address}}</h1>
        <div class="img_box">
          <img class="img" v-bind:src="item.img">
        </div>
      </div>
    </div>
  </main-layout>
</template>
<script>
import MainLayout from '../layouts/Main'//引用主页面
export default {
  data: function(){
    return{
      items: [{
        date: '2016.11.12 17:34',
        address: '北京师范大学就业指导中心141',
        img: './static/1.jpg'
      },
      {
        date: '2016.11.12 17:34',
        address: '北京师范大学就业指导中心141',
        img: './static/1.jpg'
      },
      {
        date: '2016.11.12 17:34',
        address: '北京师范大学就业指导中心141',
        img: './static/1.jpg'
      },
      {
        date: '2016.11.12 17:34',
        address: '北京师范大学就业指导中心141',
        img: './static/1.jpg'
      }]
    }
  },
  components: {
    MainLayout
  },
  computed:{
    sign_num(){
      return this.items.length;
    }
  },
  methods: {
    setImage(){
      setTimeout(function(){
        return document.getElementById("DivUp").style.display = "block";
      },5000);
    },
    imgNot(){
      return document.getElementById("DivUp").style.display = "none",
      !0
    },
    imgok(){
      var imgsrc,file_head = document.getElementById("file_head"),picture = file_head.value;
      var imgData = new Date();
      var Year = imgData.getFullYear(),
          month = imgData.getMonth()+1,
          day = imgData.getDate(),
          hour = imgData.getHours(),
          minut = imgData.getMinutes();
          month = month < 10 ? '0' + month : month;
          day = day < 10 ? '0' + day : day;
          hour = hour < 10 ? '0' + hour : hour;
          minut = minut < 10 ? '0' + minut : minut;
      console.log(imgData);
      if (!picture.match(/.jpg|.gif|.png|.bmp/i)){
       alert("您还没有选择图片或者拍照，请重新签到！");
       return document.getElementById("DivUp").style.display = "none",
        !0
      }
      imgsrc = window.navigator.userAgent.indexOf("Chrome") >= 1 || window.navigator.userAgent.indexOf("Safari") >= 1 ? window.webkitURL.createObjectURL(file_head.files[0]) : window.URL.createObjectURL(file_head.files[0]);
      var newData = { date: Year + '.' + month + '.' + day + ' ' + hour + ':' + minut , address: '',img: imgsrc};
      this.items.unshift(newData);
      return document.getElementById("DivUp").style.display = "none",
      !0
    }
  }

}
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
$color-g: rgba(233,236,239,1);/*局部的灰色*/
%fonts{
  font-size: 1.2rem;
  color: $color-gray;
}
#signin{
  background: $color-blue;
  position: relative;
  overflow: hidden;
  .line{
    position: absolute;
    left: 20%;
    margin-top: -7%;
    width: .2rem;
    height: 100%;
    background: $color-white;
    &:after{
      position: absolute;
      margin-left: -90%;
      content: '';
      display: inline-block;
      width: .5rem;
      height: .5rem;
      border-radius: 50%;
      background: $color-red;
      box-shadow:0 0 0 .3rem $color-white, 0 0 0 .4rem $color-blue;
    }
  }/*竖线*/
  header{
    position: relative;
    padding: 4% 5%;
    height: 8rem;
    background: $color-g;
    .header_sign{
      @extend %font;
      padding-left: 5%;
      line-height: 10rem;
      vertical-align: middle;
      color: $color-blue;
      span{
        margin: 0 2%;
      }/*签到数*/
    }/*签到数盒子*/
    .hader_box{
      position: absolute;
      top: 18%;
      right: 10%;
      .header_img{
        margin: 1% auto 5%;
        width: 50%;
      }/*微笑签到图片*/
      span{
        display: block;
        text-align: center;
        font-size: 1.5rem;
        font-weight: 700;
        color: $color-blue;
      }
    }/*微笑签到盒子*/
  }/*签到头部*/
  .signin_box{
    width: 58%;
    margin-left: 35%;
    padding: 3% 0;
    .sig_seria{
      position: absolute;
      margin: 5% 0 0 -16%;
      width: .7rem;
      height: .7rem;
      display: inline-block;
      border-radius: 50%;
      background: $color-g;
      box-shadow: 0 0 0 .6rem $color-blue, 0 0 0 .7rem $color-g;
    }/*序号*/
    .date{
      @extend %fonts;
      margin: 2% 0;
    }/*日期*/
    .address{
      @extend %fonts;
      margin: 3% 0;
    }/*地址*/
    .img_box{
      position: relative;
      margin: 5% 0;
      width: 100%;
      height: 20rem;
      overflow: hidden;
      border: .4rem solid $color-white;
      box-shadow: 0 0 .5rem $color-black;
    }
    .img{
      display: block;
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      margin: auto;
      max-width: 100%;
      height: 100%;
    }
  }
  #DivUp{
    position: fixed;
    top: 20%;
    left: 50%;
    z-index: 1;
    text-align: center;
    display: none;
    margin-left: -35%;
    width: 70%;
    padding: 10% 0;
    background: rgba(192,192,192,.3);
    border: .1rem solid $color-gray;
    border-radius: .3rem;
    box-shadow: 0 0 .8rem .1rem $color-gray;
    p{
      margin-bottom: 5%;
      font-size: 1.9rem;
      font-weight: 700;
      color: $color-blue;
    }/*提示文字*/
    .divup{
      margin: 0 4%;
      display: inline-block;
      padding: 3% 10%;
      font-size: 1.5rem;
      color: $color-white;
      background: $color-blue;
      border-radius: .3rem;
    }
  }/*确认取消按钮盒子*/
  #file_head{
    position: absolute;
    right: 0;
    width: 100%;
    height: 100%;
    opacity: 0;
    z-index: 1;
  }/*让文件上传覆盖整个头部*/
}
</style>