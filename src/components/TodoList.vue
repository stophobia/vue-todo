<template>
  <div id="todolistapp">
    <div id="header" class="header">
      <h2>Todo list app</h2>
      <input-todo></input-todo>
    </div>
    <list></list>
  </div>
</template>
<script>
import InputTodo from './InputTodo.vue'
import List from './List.vue'
export default {
  name: 'todo-list',
  components: {
    InputTodo,
    List
  }
}
</script>
<style>
* {
  font-family: sans-serif;
  box-sizing: box-border;
}
.header {
  background-color: #444;
  padding: 30px;
  color: #fff;
  text-align: center;
}
.header:after {
  content: '';
  display: table;
  clear: both;
}
</style>