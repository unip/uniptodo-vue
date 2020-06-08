<template>
  <div class="todo-item flex items-center bg-white px-3 overflow-hidden">
      <input class="mr-3" type="checkbox" v-on:change="toggleComplete" :checked="this.todo.completed" />
      <span class="text-left mr-auto py-2" v-bind:class="{'line-through' : todo.completed}">{{todo.title}}</span>
      <button @click="$emit('del-todo', todo.id)" class="delete">
        <i class="fas fa-times"></i>
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