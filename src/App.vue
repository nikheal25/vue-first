<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todoList" v-on:del-todo="deleteToDo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";
export default {
  name: "App",
  components: {
    Todos,
    Header
  },
  data() {
    return {
      todoList: [
        {
          id: 1,
          title: "wash cloths",
          completed: false
        },
        { id: 2, title: "trim hair", completed: false },
        { id: 3, title: "do homework", completed: true }
      ]
    };
  },
  methods: {
    deleteToDo(id) {
      this.todoList = this.todoList.filter(todo => todo.id !== id);
      console.log(id);
    }
  }
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
