<template>
  <div><h3 class="font-semibold">Todos</h3></div>
  <div class="grid grid-cols-3 md:grid-cols-4 gap-4">
    <div
      class="border-2  border-yellow-50 rounded-xl bg-green-400 p-4 text-center cursor-pointer relative"
      v-for="todo in allTodos"
      :key="todo.id"
    >
      {{ todo.title }}
      <i
        @click="deleteTodo(todo.id)"
        class="fas fa-trash-alt right-2 bottom-2 absolute text-white"
      ></i>
    </div>
  </div>
</template>
<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "Todos",
  methods: { ...mapActions(["fetchTodos", "deleteTodo"]) },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  },
};
</script>
