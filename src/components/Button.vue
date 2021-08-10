<template>
	<button @click="onClick()" class="btn" :style="{background:color}">{{text}}</button>
</template>

<script>
	export default {
		name:'Button',
		props:{
			color:String,
			text:String
		},
		methods:{
			onClick(){
				console.log('click')
			}
		}
	}
</script>
