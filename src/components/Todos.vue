<template>
  <div class="rounded shadow-lg overflow-hidden mb-4">
    <TodoItem
      :key="todo.id"
      v-for="todo in todos.sort((a, b) => a.completed - b.completed)"
      :todo="todo"
      @del-todo="$emit('del-todo', todo.id)"
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