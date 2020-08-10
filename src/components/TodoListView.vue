<template>
  <ul id="sortable" class="list-unstyled">
    <li class="ui-state-default" v-for="todo in todos" :key="todo.id">
      <div class="checkbox">
        <label>
          <input type="checkbox" @click="doneTodo(todo.id)" />{{todo.title}}
        </label>
      </div>
    </li>
</ul>
</template>

<script>
export default {
  name: 'TodoListView',
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  methods: {
    doneTodo(todoId) {
      // EventBus.$emit('completed-todo', {id: todoId})
      this.$store.dispatch('completeTodo', {id: todoId});
    }
  }

}
</script>

<style>

</style>