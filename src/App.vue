<template>
  <h1>Todo Aplication</h1>
  <AddTodo @add-todo="addTodd" />
  <hr />
  <TodoList v-bind:todos="todos" @remove-todo="removeTodo" />
  <!-- v-bind в качестве пропс нужен для передачи данных todos каторый написан в ковычках это и есть массив todos -->
  <!-- а для того чтиобы взять эти данные в todolist нужно запомнить todos после двоеточых -->
</template>

<script>
import TodoList from "@/components/TodoList";
import AddTodo from "@/components/AddTodo";
export default {
  name: "App",
  data() {
    return {
      todos: [
        { id: 1, title: "Buy bred", completed: false },
        { id: 2, title: "Buy butter", completed: false },
        { id: 3, title: "Buy tea", completed: false },
      ],
    };
  },
  components: {
    TodoList,
    AddTodo,
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=3")
      .then((response) => response.json())
      .then((json) => {
        this.todos = json;
      });
  },git 
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addTodd(todo) {
      this.todos.push(todo);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
