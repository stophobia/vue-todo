<template lang="pug">
  div
    h1 Todo
    h3 {{ (new Date()).toTimeString() }}
    InputTodo
    hr
    List
</template>
<script>
import InputTodo from './InputTodo.vue'
import List from './List.vue'
export default {
  name: 'todolist',
  components: {
    InputTodo,
    List
  }
}
</script>
<style lang="sass" scoped>
@import '../assets/common.sass'
.header
  background-color: #444
  padding: 30px
  color: #fff
  text-align: center
.header:after
  content: ''
  display: table
  clear: both
</style>
