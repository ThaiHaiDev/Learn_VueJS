<template>
  <MenuTest :dataSend="todoList" />
</template>

<script>
import MenuTest from "./components/MenuTest.vue";

export default {
  name: "App",
  components: {
    MenuTest,
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
