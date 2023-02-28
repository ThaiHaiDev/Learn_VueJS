<template>
  <div>
    <div class="list-task">
      <input type="text" v-model="newTask" />
      <button v-on:click="addTask">Add</button>
    </div>
    <div v-for="(task, index) in Tasks" :key="index">
      <p>{{ task }}</p>
    </div>
  </div>
</template>

<script>
import { useTodoStore } from "../pinia/store/todo";
import { defineComponent } from "vue";

export default defineComponent({
  name: "ListTask",
  data() {
    return {
      newTask: "he",
      Tasks: ["Learn React", "Learn Vue", "Learn Node"],
    };
  },
  setup() {
    const todoStore = useTodoStore();
    // console.log(counterStore.count)
    return { todoStore };
  },
  mounted() {},
  methods: {
    addTask() {
      // Tasks.push(task)
      // console.log(this.storeTodo.count)
      // this.storeTodo().addTodo('ge', 'test');
      this.todoStore.addTodo('test', 'test')
      console.log("New Count:", this.todoStore.totalTodos);
    },
  },
});
</script>

<style>
.list-task {
  display: flex;
}
</style>
