<template>
  <div class="hello">
    <h1>Day la Menu</h1>
    <!-- Two way binding -->
    <input type="text" v-model="name"/>
    <h3>{{ name }}</h3>

    <h1 v-show="isShow">Show name</h1>
    <button @click="isShow = !isShow">Show</button>

    <h1 :class="{ daChon : selected }">Da chon style</h1>
    <button @click="selected = !selected">Chon style</button>

    <h2 :class="{ eventClick : testEvent }" v-on:click="() => { testEvent = !testEvent }">Event click</h2>

    <div v-for="(task, index) in dataSend" :key="index">
      <p v-on:click="() => { handleDemo(task) }">{{ task }}</p>
    </div>
  </div>
</template>

<script>
export default {
    name: 'MenuTest',
    props: {
      dataSend: [],
    },
    data() {
      return {
        name: 'Thai Hai',
        isShow: true,
        selected: true,
        testEvent: false,
        todoList: [
          'ReactJS',
          'VueJS',
          'NodeJS'
        ]
      }
    },
    // Chay dau tien khi load, giong useEffect, dung de call Api
    mounted() {

    },
    methods: {
      handleDemo: (task) => {
        console.log('Function test', task)
      }
    },
    watch: {
      // Khi data name thay doi thi thuc hien
      name: function(newValue, oldValue) {
        console.log('name change')
        console.log(newValue, oldValue)
      }
    }
};
</script>

<style>
.daChon {
  color: red;
}

.eventClick {
  color: blue;
  cursor: pointer;
}
</style>
