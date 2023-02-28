<template>
  <div>
    <MenuTest :dataSend="todoList" />
    <hr />
    <ListTask />
  </div>

</template>

<script>
import MenuTest from "./components/MenuTest.vue";
import ListTask from "./components/ListTask.vue";

export default {
  name: "App",
  components: {
    MenuTest,
    ListTask
  },
  data() {
    return {
      todoList: ["ReactJS", "VueJS", "NodeJS"],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
