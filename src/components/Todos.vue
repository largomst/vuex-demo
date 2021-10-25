<template>
  <div>
    <h3 class="font-semibold">Todos</h3>
    <div class="flex justify-around mb-4">
      <span>Double click to mark as complete</span>
      <span>
        <span class="inline-block bg-green-400 w-3 h-3"></span>
        = Incomplete
      </span>
      <span>
        <span class="inline-block bg-gray-400   w-3 h-3"></span> = Complete
      </span>
    </div>
  </div>
  <div class="grid grid-cols-3 md:grid-cols-4 gap-4">
    <div
      @dblclick="onDblClick(todo)"
      :class="[todo.completed ? 'bg-gray-400' : 'bg-green-400', { todo: true }]"
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
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed,
      };
      this.updateTodo(updTodo);
    },
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  },
};
</script>

<style scoped>
.todo {
  @apply border-2  border-yellow-50 rounded-xl  p-4 text-center cursor-pointer relative;
}
</style>
