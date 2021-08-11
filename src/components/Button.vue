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
				this.$emit('toggle-add-task')
			}
		}
	}
</script>
