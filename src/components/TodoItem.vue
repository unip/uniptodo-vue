<template>
  <div class="todo-item flex items-center bg-white hover:bg-gray-100 px-3 overflow-hidden">
      <input class="mr-3" type="checkbox" @change="toggleComplete" :checked="this.todo.completed" />
      <span class="text-left mr-auto py-2" :class="{'line-through opacity-25' : todo.completed}">{{todo.title}}</span>
      <button @click="$emit('del-todo', todo.id)" class="delete">
        <i class="fas fa-times-circle fa-fw"></i>
      </button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    toggleComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style scoped>
</style>