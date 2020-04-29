<template>
  <div class v-bind:class="{'is-completed':dataItem.completed}">
    <p>{{dataItem.title}}</p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["dataItem"]
};
</script>

<style scoped>
.is-completed {
  text-decoration: line-through;
}
</style>