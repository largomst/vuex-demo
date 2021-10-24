<template>
  <div>
    <h3 class="font-semibold">Add Todo</h3>
    <div>
      <form class="flex" @submit="onSubmit">
        <input
          class="flex-grow border-2 focus:outline-none focus:border-green-500 border-green-400  p-2 "
          type="text"
          v-model="title"
          placeholder="Add Todo..."
        />
        <input
          class="flex-grow-0 w-24 bg-green-400 hover:bg-green-500  cursor-pointer text-white"
          type="submit"
          value="Submit"
        />
      </form>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
      this.title = "";
    },
  },
};
</script>
