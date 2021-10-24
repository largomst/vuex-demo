<template>
  <div>
    <div class="container mx-auto px-2">
      <Todos />
    </div>
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
export default {
  name: "App",
  components: { Todos },
};
</script>

<style></style>
