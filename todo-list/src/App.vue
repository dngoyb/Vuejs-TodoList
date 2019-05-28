<template>
  <div id="app">
    <Header></Header>
    <AddTodo @add-todo="addTodo"></AddTodo>

    <Todos :todos="todos" @del-todos="deleteTodo"></Todos>
  </div>
</template>

<script>
import Header from './components/Header'
import AddTodo from './components/AddTodo'
import Todos from './components/Todos'
export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodo
  },
  
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'First todo title',
          completed: false
        },
        {
          id: 2,
          title: 'Second todo title',
          completed: true
        },
        {
          id: 3,
          title: 'Third todo title',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
       this.todos = [...this.todos, newTodo]
      console.log("hello world")
    }
  },
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing:border-box;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}


</style>
