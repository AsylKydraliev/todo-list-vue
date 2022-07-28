<template>
  <div id="app">
    <div class="container">
      <h1>Todo application</h1>
      <AddTodo />
      <hr>
      <TodoList
          v-bind:todos="todos"
          @remove-todo="removeTodo"
      />
    </div>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList';
import AddTodo from "@/components/AddTodo";
export default {
  name: 'App',
  data () {
    return {
      todos : [
        {id: 1, title: 'Купить хлеб', completed: false},
        {id: 2, title: 'Купить масло', completed: false},
        {id: 3, title: 'Купить пиво', completed: false},
      ]
    }
  },
  components: {
    AddTodo,
    TodoList
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
  max-width: 1000px;
  margin: 60px auto 0;
}
</style>
