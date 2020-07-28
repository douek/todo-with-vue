<template>
  <v-app>
    <v-container>
      <div class="text-h6" v-text="count"></div>
    </v-container>
    <CreateTodo @addTodo="addTodo"></CreateTodo>
    <todoList :todos="todos" @removeTodo="removeTodo"></todoList>
  </v-app>
</template>

<script>
import todoList from "./components/todoList";
import CreateTodo from "./components/createTodo";

export default {
  name: "App",

  components: {
    todoList,
    CreateTodo,
  },

  data() {
    return {
      todos: [{ text: "hi" }, { text: "pink" }],
    };
  },
  methods: {
    removeTodo(item) {
      let index = this.todos.indexOf(item);
      this.todos.splice(index, 1);
    },
    addTodo(item) {
      let todo = { text: item };
      this.todos.push(todo);
    },
  },
  computed: {
    count() {return `Todos left: ${this.todos.length}`}
  }
};
</script>
