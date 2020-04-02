<template lang="pug">
  ul
    li(
      v-for="(a, i) in todolist"
      v-bind:class="checked(a.done)"
      v-bind:key=i
      v-on:click="doneToggle(i)"
    )
      span {{a.todo}}
      span(
        v-if="a.done"
      )  [ DONE ]
      span.close(
        v-on:click.stop="deleteTodo(i)"
      ) &#x00D7;
</template>

<script>
import eventBus from './EventBus.vue'
export default {
  created() {
    eventBus.$on('add-todo', this.addTodo)
  },
  data() {
    return {
      todolist: [
        {
          todo: "go cinema",
          done: false,
        },
        {
          todo: "go picnic",
          done: true,
        },
        {
          todo: "study english",
          done: false,
        },
        {
          todo: "go baseball",
          done: false,
        },
      ]
    }
  },
  methods: {
    checked: function(done) {
      if (done) {
        return {
          checked: true
        }
      } else {
        return {
          checked: false
        }
      }
    },
    addTodo: function(todo) {
      if (todo !== '') {
        this.todolist.push({
          todo: todo,
          done: false,
        })
      }
    },
    doneToggle: function(i) {
      this.todolist[i].done = !this.todolist[i].done
    },
    deleteTodo: function(i) {
      this.todolist.splice(i, 1)
    }
  }
}
</script>

<style lang="sass" scoped>
@import '../assets/common.sass'
ul
  margin: 0
  padding: 0
  li
    cursor: pointer
    position: relative
    margin-bottom: 2px
    padding: 8px
    background-color: $primary_color
    font-size: 14px
    transition: 0.2s
    -webkit-user-select: none
    -moz-user-select: none
    -ms-user-select: none
    user-select: none
    border-radius: 2px
    span
      color: $white
    &:hover
      background-color: $primary_color_hover
    &.checked
      background-color: $primary_color_hover
      span
        text-decoration: line-through
      &::before
        content: ''
        position: absolute
        border-color: $white
        border-style: solid
        border-width: 0 1px 1px 0
        top: 10px
        left: 16px
        transform: rotate(45deg)
        height: 8px
        width: 8px
.close
  position: absolute
  right: 0
  top: 0
  padding: 8px 12px
  &:hover
    background-color: $error_color
    color: $white
</style>
