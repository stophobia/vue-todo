<template lang="pug">
  div
    input(
      type="text"
      v-model.trim="todo"
      placeholder="Input and enter"
      v-on:keyup.enter="addTodo"
    )
    span.addbutton(
      v-on:click="addTodo"
    ) Add
</template>
<script>
import eventBus from './EventBus.vue'
export default {
  name: 'input-todo',
  data: function() {
    return {
      todo: ""
    }
  },
  methods: {
    addTodo: function() {
      eventBus.$emit('add-todo', this.todo)
      this.todo = ''
    }
  },
}
</script>
<style lang="sass">
@import '../assets/common.sass'
input
  border: none
  width: 75%
  height: 35px
  padding: 10px
  float: left
  font-size: 16px
  background: $pale_grey
.addbutton
  padding: 10px
  width: 25%
  height: 35px
  background-color: $main_color
  color: $white
  float: left
  text-align: center
  line-height: 1
  &:hover
    background-color: $main_color_hover
    cursor: pointer
</style>
