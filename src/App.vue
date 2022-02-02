<template>
  <div>
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-on:delete-todo="deleteTodo" v-on:update-todo="updateTodo" v-bind:todos="todos" />
    
  </div>
</template>

<script>
import AddTodo from "./components/AddTodo.vue";
import Todos from "./components/Todos.vue";


export default {
  name: "App",
  components: {
    AddTodo,
    Todos,
    

  },
  data() {
    return {
      todos: [
        {
          id: "1",
          title: "i have to learn coding",
          completed: false,
        },
        {
          id: "2",
          title: "i will go for market",
          completed: true,
        },
        {
          id: "3",
          title: "there is some official work i have to compleate",
          completed: false,
        },
        {
          id: "4",
          title: "physical exercise",
          completed: true,
        },
      ],
    };
  },
  methods: {
    addTodo(todo) {
      this.todos = [...this.todos, todo];
    },

    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    updateTodo(id){
     const todo =this.todos.find((todo)=>todo.id===id)
     todo.completed= !todo.completed
    }
  },
};
</script>

