<template>
		<li>
			
				<span class='text'>{{i.text}}</span>
				<button @click='$emit("delTodo", i.id)'>&times;</button>
			
		</li>
</template>

<script>

	export default{
		props: {
		i:Object,
		todo:Array
	}, 
	}


</script>

<style>
.text{
	margin-right: 10px;
}
li{
	margin-bottom: 10px; 
	width: 700px;
	margin-left: 42%;
	padding-left: 0px;
	text-align: left;

}
</style>