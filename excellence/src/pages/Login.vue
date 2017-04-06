<template>
	<main-layout>
	  <div id="login">
	  	<img src="../assets/m_logo.png">
		<v-link href="/Home">
			<button>微信一键登录</button>
		</v-link>
	    <p>还没有英才帐号？<span>快速注册</span></p>
	  </div>
	</main-layout>
</template>

<script>
import MainLayout from '../layouts/Main'//引用主页面
import VLink from '../components/VLink' /*引用跳转封装*/
export default {
	data: function(){
	  return{
	    
	  }
	},
  components: {
    MainLayout,
    VLink
  }
}
</script>
<style lang="scss">
@import "../components/mixin";
	#login{
		overflow: hidden;
		img{
			display: block;
			margin: 10% auto;
			width: 50%;
			height: auto;
		}/*图片logo*/
		button{
			display: block;
			margin: 0 auto;
			padding: 4% 20%;
			border-radius: .2rem;
			font-size: 1.7rem;
			font-weight: 700;
			color: rgba(248,248,248,.8);
			background: $color-green;
		}/*微信登录*/
		p{
			margin: 5% 0;
			text-align: center;
			font-weight: bold;
			font-size: 1.5rem;
			letter-spacing: 0;
			color: $color-gray;
			span{
				margin-left: 2%;
				color: $color-blue;
			}
		}
	}
</style>