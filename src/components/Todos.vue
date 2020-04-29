<template>
  <div>
    <h1>TODOS</h1>
    <br />
    <div v-for="item in todos" v-bind:key="item.id">
      <h3>{{item.id}}</h3>
      <TodoItem v-bind:dataItem="item" />
      <hr />
    </div>
  </div>
</template>


<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>

<style scoped>
</style>