<template>
	<header>
		<h1>{{title}}</h1>
		<Button @toggle-add-task="$emit('toggle-add-task')" text="Add Button" color="green"/>
	</header>
</template>

<script>
	import Button from './Button.vue'
	export default {
		name:'Header',
		components:{
			Button
		},
		props:{
			title: String
		}
	}
</script>

<style>
	header{
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 20px;
	}
</style>