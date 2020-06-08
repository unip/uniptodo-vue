<template>
  <form v-on:submit.prevent="addTodo" class="w-full sticky bottom-0 left-0 pb-4">
    <div class="flex bg-white rounded shadow-lg overflow-hidden">
      <input type="text" v-model="title" name="title" placeholder="Add todo..." class="py-3 px-3 w-full">
      <input type="submit" value="Submit" class="px-3 bg-green-600 hover:bg-green-500 text-white cursor-pointer">
    </div>
  </form>
</template>

<script>
// import { v4 as uuidv4 } from 'uuid'

export default {
  name: 'AddTodo',
  data() {
    return {
      title: '',
    }
  },
  methods: {
    addTodo() {
      const newTodo = {
        // id: uuidv4(),
        title: this.title,
        completed: false
      }
      this.$emit('add-todo', newTodo)
      this.title = ''
    }
  }
}
</script>

<style>

</style>