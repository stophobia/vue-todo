<template lang="pug">
  div.container
    header
      nav
        ul
          li: a(
            href="#"
            v-if="this.currentView === 'todolist' ? 'class=this' : 'class'"
            v-on:click="changeMenu('todolist')"
            ) HOME
          li: a(
            href="#"
            v-if="this.currentView === 'about' ? 'class=this' : 'class'"
            v-on:click="changeMenu('about')"
          ) About
          li: a(
            href="#"
            v-if="this.currentView === 'contact' ? 'class=this' : 'class'"
            v-on:click="changeMenu('contact')"
          ) Contact
    div
      keepAlive(
        include="todolist, about, contact"
      )
        component(
          v-bind:is="currentView"
        )
</template>

<script>
import Todolist from './components/TodoList.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'app',
  components: {
    Todolist,
    About,
    Contact,
  },
  data() {
    return {
      currentView: 'todolist'
    }
  },
  methods: {
    changeMenu(view) {
      this.currentView = view
    }
  }
}
</script>

<style lang="sass" scoped>
@import './assets/common.sass'
.container
  width: 320px
  margin: 0 auto
  padding: 0 20px
  header
    margin: 10px 0
  ul
    list-style: none
    margin: 0
    padding: 0
    overflow: hidden
    background-color: $white
    li
      float: left
      padding: 10px
      a
        display: block
        color: $text_color
        text-align: center
        padding: 10px
        text-decoration: none
        &:hover,
        &.this
          background-color: $light_grey
          color: $text_color_hover
</style>
