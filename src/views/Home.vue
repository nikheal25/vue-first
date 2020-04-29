<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todoList" v-on:del-todo="deleteToDo" />
    <AddTodo v-on:add-todo="addNewTodo" />
  </div>
</template>

<script>
import Todos from "../components/Todos";
import Header from "../components/layout/Header";
import AddTodo from "../components/AddTodo";

export default {
  name: "App",
  components: {
    Todos,
    Header,
    AddTodo,
  },
  data() {
    return {
      todoList: [
        {
          id: 1,
          title: "wash cloths",
          completed: false,
        },
        { id: 2, title: "trim hair", completed: false },
        { id: 3, title: "do homework", completed: true },
      ],
    };
  },
  methods: {
    deleteToDo(id) {
      this.todoList = this.todoList.filter((todo) => todo.id !== id);
      console.log(id);
    },
    addNewTodo(item) {
      console.log("hello");

      this.todoList = [...this.todoList, item];
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.4;
}
</style>
