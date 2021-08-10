<template>
	<div @dblclick="$emit('toggle-reminder' , task.id)" :class="[task.reminder ? 'reminder' : '','task']">
		<div class="head-body">
		<h3>{{task.text}}</h3>
		<i @click="$emit('delete-task' , task.id)" class="fas fa-times" style="color: red;"></i>
		</div>
		<small>{{task.day}}</small>
	</div>
</template>

<script>
	export default {
		name:'Task',
		props:{
			task:Object
		},
		
	}
</script>

<style scoped>
small{
	color: #888;
	}
	.task{
		background:#f4f4f4;
		margin: 5px;
		padding: 10px 20px;
		cursor: pointer;
	}
	.task.reminder{
		border-left: 5px solid green;
	}
	.task .head-body{
		display: flex;
		align-items: center;
		justify-content: space-between ;
	}
</style>
