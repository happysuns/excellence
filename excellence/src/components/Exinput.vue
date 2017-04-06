<template>
	<div>
		<h1>{{school.title}}</h1>
		<input class="school" v-model="school.data" placeholder="学校">
	</div>
</template>

<script>
	export default{
		data:function(){
			return{

			}
		},
		props: ['school']
	}
</script>