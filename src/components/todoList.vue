<template>
    <v-container>
        <v-row >
            <v-col  cols="12" v-for="(todo, i) in todos" :key="i">
            <todoItem :todo="todo" @itemDelete="removeTodo"></todoItem>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import todoItem from './todoItem.vue'

export default {
    name: 'todoList',
    components: {
        todoItem,
    },
    props: {
        todos: Array
    },
    methods: {
        removeTodo(item) {
            console.log('remove todo on list')
            console.log('the todo is ', item)
            this.$emit('removeTodo', item)
        }
    }
}
</script>