<template>
  <div class="todolist">
    <h1>Already Done</h1>
    <ul id="done-items" class="list-unstyled">
      <li v-for="todo in todos" :key="todo.id">{{todo.title}}
        <button class="remove-item btn btn-default btn-xs pull-right" @click="removeToto(todo.id)">
          <i class="fa fa-trash"></i>
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'FinishedTodos',
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  methods: {
    removeToto(todoId){
      // EventBus.$emit('delete-todo', {id: todoId})
      this.$store.dispatch('deleteTodo', {id: todoId});
    }
  }
}
</script>

<style>

</style>