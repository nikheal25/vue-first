<template>
  <div>
    <form @submit="addToDoList">
      <input
        type="text"
        v-model="newTask"
        name="newTask"
        placeholder="New Todo..."
      />
      <button type="submit" value="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuid } from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      newTask: "",
    };
  },
  methods: {
    addToDoList(e) {
      e.preventDefault();
      console.log("Hello");

      const newTodo = {
        id: uuid(),
        title: this.newTask,
        completed: false,
      };
      //   //send the object
      console.log(newTodo);

      this.$emit("add-todo", newTodo);

      this.newTask = "";
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
}

button {
  display: inline-block;
  border: none;
  background: black;
  color: aliceblue;
  padding: 10px;
}
</style>
