<template>

  <div id="app">
    {{ msg }}
    <div>
      <input type="text" v-model="info" />
      <button @click="handleClick">添加</button>
    </div>
    <ul>
      <todo-item v-for="item in list" :key="item">
        <template v-slot:item="itemProps">
          <span :style="{ fontSize: '20px', color: itemProps.checked ? 'red' : 'blue' }">{{ item }}</span>
        </template>
      </todo-item>
    </ul>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TodoItem from './components/TodoItem'
export default {
  name: "app",
  data() {
    return {
      msg: "hello msg",
      info: "",
      list: [],
    };
  },
  methods: {
    handleClick() {
      console.log(this.info);
      this.list.push(this.info);
      this.info = "";
    },
  },
  components: {
    TodoItem,
  },
};
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
