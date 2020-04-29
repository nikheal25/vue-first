<template>
  <div id="app">
    <Todos v-bind:todos="todoList" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
export default {
  name: "App",
  components: {
    Todos
  },
  data() {
    return {
      todoList: [
        {
          id: 1,
          title: "wash cloths",
          completed: false
        },
        { id: 2, title: "trim hair", completed: false }
      ]
    };
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
