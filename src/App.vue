<template>
  <v-app>
    <CreateTodo @addTodo="addTodo"></CreateTodo>
    <todoList :todos='todos' @removeTodo="removeTodo"></todoList>
  </v-app>
</template>

<script>
import todoList from './components/todoList';
import CreateTodo from './components/createTodo'

export default {
  name: 'App',

  components: {
    todoList,
    CreateTodo,
  },

  data: () => ({
    todos: [{text: 'hi'}, {text:'pink'}]
  }),
  methods:{
    removeTodo(item){
      let index = this.todos.indexOf(item)
      this.todos.splice(index,1)
    },
    addTodo(item){
      let todo = {text: item}
      this.todos.push(todo)
    }
  }
};
</script>
