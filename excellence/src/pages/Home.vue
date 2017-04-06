<template>
  <main-layout>
    <div id="home">
      <img class="home_img" src="../assets/m_logo.png">
      <naviga></naviga>
      <p class="home_txt">职业养成及精准就业服务平台 <span v-text="num"></span></p>
    </div>
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue'//引用主页面
  import naviga from '../components/naviga'//引用导航

  export default {
  	data: function(){
  	  return{
  	    num: 'v1.0'
  	  }
  	},
    components: {
      MainLayout,
      naviga
    }
  }
</script>

<style lang="scss">
@import "../components/mixin";//引用变量、方法
html,body{height: 100%;}
.container{
  width: 100%;
  height: 100%;
}
#home{
  width: 100%;
  height: 100%;
  display: webkit-box;
  display: flex;
  flex-direction: column;
  background: rgba(20,49,79,1);
  .home_img{
    width: 28%;
    height: auto;
    padding-top: 10%;
    margin: 0 auto 10%;
  }/*logo*/
  .naviga{
    flex: 2;
  }/*导航*/
  .home_txt{
    text-align: center;
    font-size: 1.2rem;
    font-weight: 700;
    color: $color-gray;
    flex: .2;
  }/*文本*/
}
</style>