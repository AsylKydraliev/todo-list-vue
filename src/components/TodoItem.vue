<template>
  <li>
    <span v-bind:class="{done: todo.completed}">
      <input
          type="checkbox"
          v-on:change="todo.completed = !todo.completed">
      <strong>{{ todo.id }}</strong>
      {{ todo.title }}
    </span>
    <button
        class="btn"
        v-on:click="$emit('remove-todo', todo.id)"
    >&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
  li {
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: 0.5rem 2rem;
    margin-bottom: 1rem;
  }

  .btn {
    background: red;
    color: #fff;
    border: none;
    border-radius: 20%;
    font-weight: bold;
  }

  input {
    margin-right: 1rem;
  }

  .done {
    text-decoration: line-through;
  }
</style>