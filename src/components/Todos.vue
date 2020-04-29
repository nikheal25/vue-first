<template>
  <div>
    <h1>TODOS</h1>
    <div v-for="item in todos" v-bind:key="item.id">
      <h3>{{item.title}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todos",
  props: ["todos"]
};
</script>

<style scoped>
</style>