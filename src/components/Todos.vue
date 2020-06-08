<template>
  <div class="rounded shadow-lg overflow-hidden mb-4">
    <TodoItem
      v-bind:key="todo.id"
      v-for="todo in todos"
      v-bind:todo="todo"
      v-on:del-todo="$emit('del-todo', todo.id)"
    />
  </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  name: 'Todos',
  props: ['todos'],
  components: {
    TodoItem,    
  }
}
</script>

<style>

</style>