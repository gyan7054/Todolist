<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <Todoitem
        v-on:delete-todo="$emit('delete-todo', todo.id)"
        v-on:update-todo="$emit('update-todo', todo.id)"
        v-bind:todo="todo"
      />
    </div>
  </div>
</template>


<script>
import Todoitem from "./Todoitem.vue";
export default {
  name: "Todos",
  props: ["todos"],
  components: {
    Todoitem,
  },
};
</script>

<style scoped>
</style>