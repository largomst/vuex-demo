<template>
  <div><h3 class="font-semibold">Todos</h3></div>
  <div class="grid grid-cols-3 gap-4">
    <div
      class="border-2  border-yellow-50 rounded-xl bg-green-400 p-4 text-center cursor-pointer "
      v-for="todo in allTodos"
      :key="todo.id"
    >
      {{ todo.title }}
    </div>
  </div>
</template>
<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "Todos",
  methods: { ...mapActions(["fetchTodos"]) },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  },
};
</script>
