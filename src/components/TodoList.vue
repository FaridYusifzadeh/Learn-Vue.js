<template>
  <div>
    <ul>
      <TodoItem
        v-for="todo in todos"
        v-bind:key="todo.id"
        v-bind:todo="todo"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
  <!-- remove-todo это отправланное событие из Todo Item -->
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
  // а тут в пропсе мы указываем todos каторый отправили как пропс в этот компонент
  // а чтобы вывести данные пропса нукжно писать тодус в {{}}
  //   могут возникнуть проблемы нужно передавать v bind key как и в реакт
  props: ["todos"],
  components: {
    TodoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit("remove-todo", id);
    },
  },
};
</script>

<style scoped>
ul {
  margin: 0;
  padding: 0;
}
</style>
