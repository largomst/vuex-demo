<template>
  <div>
    <div class="container mx-auto px-2">
      <AddTodo class="mt-4 mb-4" />
      <FilterTodo />
      <Todos />
    </div>
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";
import FilterTodo from "./components/FilterTodo.vue";
export default {
  name: "App",
  components: { Todos, AddTodo, FilterTodo },
};
</script>

<style></style>
