<template>
  <v-container>
    <v-form>
      <v-row>
        <v-col  cols="10">
          <v-text-field v-model="todo" :rules="[rules.required]" label="NEW Todo"></v-text-field>
        </v-col>
        <v-col cols="2">
          <v-btn color="success" @click="addNew" class="mr-4">Add</v-btn>
        </v-col>
      </v-row>
    </v-form>
  </v-container>
</template>

<script>
export default {
  name: "CreateTodo",
  data: () => {
    return {
        todo: '',
      rules: {
        required: (value) => !!value || "Required.",
      },
    };
  },
  methods: {
      addNew(){ 
          let todoText =this.todo
          this.todo =''
          this.$emit('addTodo', todoText)
      }
  }
};
</script>