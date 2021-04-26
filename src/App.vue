<template>
  <h1>Todo Aplication</h1>
  <hr />
  <TodoList v-bind:todos='todos'/> 
  <!-- v-bind в качестве пропс нужен для передачи данных todos каторый написан в ковычках это и есть массив todos -->
  <!-- а для того чтиобы взять эти данные в todolist нужно запомнить todos после двоеточых -->
</template>

<script>
import TodoList from "@/components/TodoList";
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
