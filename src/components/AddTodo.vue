<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Create</button>
  </form>
  <!--submit.prevent это как юы prevent default не дает обновляться странице   -->
  <!-- v-model для получения даты из инпута и записывания в title в скрипте даты   -->
</template>
<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    onSubmit() {
      console.log("Hello", this.title);
      if (this.title.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false,
        };
        this.$emit("add-todo", newTodo);
        this.title = "";
      }
    },
  },
};
</script>
<style scoped>
form {
  display: flex;
}
input {
  width: 400px;
}
</style>
