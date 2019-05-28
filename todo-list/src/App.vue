<template>
  <div id="app">
    <Todos :todos="todos" @del-todos="deleteTodo"></Todos>
  </div>
</template>

<script>
import Todos from './components/Todos'
export default {
  name: 'app',
  components: {
    Todos
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
      console.log(this.todos)
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}


</style>
