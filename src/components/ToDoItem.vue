<template>
	<div>
		<input @change='onChange' class='input' type="text" placeholder="New todo" v-model='text'>
		
		<ul>
			<list
			v-for="i in todo"
			v-bind:i='i'
			:key="i.id"
			v-bind:todo='todo'
			@delTodo='deleteTodo'
		/>
		</ul>
	</div>
</template>


<script>
import list from '@/components/list'
	
	export default{
		props:{
			todo: Array,
		},
		components: {
			list,
		},
		data(){
			return{
				text: '',
				id: 1,
			}
		},
	
		methods: {
			onChange(){
				if (this.text.trim()){
					let newTodo = {
						id: this.id++,
						text: this.text,
					}
				this.$emit('add-todo', newTodo)
				this.text = ''
				this.id = this.id++
				}
			},
			deleteTodo(id){
			this.$emit('delete-to-do', id)	
		}
		}
	}

</script>


<style scoped>
.input{
	line-height: 24px;
	padding-left: 10px;
	width: 350px;
}
ul{
	padding-left: 0px;
}
</style>