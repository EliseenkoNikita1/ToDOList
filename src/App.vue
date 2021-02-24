<template>
  <div id="app">
    <h1>My Todo App!</h1>
    <ToDoItem @delete-to-do='deleteToDo' @add-todo='addTodo' v-bind:todo="todos"/>
  </div>
</template>

<script>

import ToDoItem from '@/components/ToDoItem'
export default {
  name: 'App',
  components: {
    ToDoItem
  },
  methods:{
    addTodo(todo){
      this.todos.push(todo);
    },
    deleteToDo(id){
      this.todos = this.todos.filter(i => i.id != id)
    }
  },
  data(){
    return{
      todos: [
        
        ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
