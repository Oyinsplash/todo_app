<template>
  <div id="app">
    
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from '../components/Todos'
import AddTodo from '../components/Addtodo'

export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return{
          todos: [ ]
    }
  },
  methods:
  {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo=>todo.id !== id));
    },
    addTodo(newTodo) {
      this.todos = [newTodo,...this.todos];
    }
  },
  created() {
        fetch('https://jsonplaceholder.typicode.com/users/1/todos?_limit=6')
        .then((res)=>res.json())
        .then((json)=> this.todos = json)
        .catch((error=> console.log(error)))
    }
  
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0 }

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 2px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>
