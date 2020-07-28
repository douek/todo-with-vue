<template>
  <v-card color="red lighten-2">
      <div>
        <v-row align="center">
          <v-col cols="11">
            <v-card-text class="headline font-weight-bold" v-text="todo.text"></v-card-text>
          </v-col>
          <v-col cols="1" class="aligh-end">
            <v-btn icon @click="deleteItem" class="aligh-end">
              <v-icon>mdi-close</v-icon>
            </v-btn>
          </v-col>
        </v-row>
      </div>
  </v-card>
</template>



<script>
export default {
  name: "todoItem",
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  methods: {
    deleteItem() {
      this.$emit("itemDelete", this.todo);
    },
  },
};
</script>