<template>
  <div id="home" class="flex-grow">
    <div class="container flex flex-col h-full mx-auto pt-4 px-4">
      <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
      <AddTodo v-on:add-todo="addTodo" />
    </div>
  </div>
</template>

<script>
  import AddTodo from '../components/AddTodo'
  import Todos from '../components/Todos'
  import axios from 'axios'

  export default {
    name: 'Home',
    components: {
      Todos,
      AddTodo,
    },
    data() {
      return {
        todos: []
      }
    },
    methods: {
      deleteTodo(id) {
        axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
          .then(() => this.todos = this.todos.filter(todo => todo.id !== id))
          .catch(err => console.log('Error!', err))
      },
      addTodo(newTodo) {
        const { title, completed } = newTodo
        axios.post('https://jsonplaceholder.typicode.com/todos', {
          title,
          completed
        })
          .then(res => this.todos = [...this.todos, res.data])
          .catch(err => console.log('Error!', err))
      }
    },
    created() {
      axios.get('https://jsonplaceholder.typicode.com/todos?_limit=20')
        .then(res => this.todos = res.data)
        .catch(err => console.log('Error!', err))
    }
  }
</script>
