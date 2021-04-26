<template>
  <li>
    <span v-bind:class="{ done: todo.completed }">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
      <strong>{{ todo.id }}</strong>
      {{ todo.title }}
    </span>
    <button class="btn-delete" v-on:click="$emit('remove-todo',todo.id)">
      &times;
    </button>
  </li>
  <!-- для того чтобы сообщить родительскому элементу что у нас чтота случилось обращаемся к функции $emit('remove-todo')  первым параметром придумываем названия события а втарым некоторые данные  -->
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}
.btn-delete {
  background: red;
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
  outline: none;
}
input {
  margin-right: 1rem;
}
.done {
  text-decoration: line-through;
}
</style>
