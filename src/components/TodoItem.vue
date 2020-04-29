<template>
  <div>
    <p v-bind:class="{'is-completed':dataItem.completed}">
      <input type="checkbox" v-on:change="markCompleted" />
      {{dataItem.title}}
    </p>
    <p>{{dataItem.completed}}</p>
    <button @click="$emit('delete-todo', dataItem.id)">DELETE</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["dataItem"],
  methods: {
    markCompleted() {
      this.dataItem.completed = !this.dataItem.completed;
    }
  }
};
</script>

<style scoped>
.is-completed {
  text-decoration: line-through;
}
</style>