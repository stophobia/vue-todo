<template>
  <div>
    <div class="header">
      <h1 class="headerText">Todo List App</h1>
      <nav>
        <ul>
          <li>
            <a href="#" v-on:click="changeMenu('todolist')">HOME</a>
          </li>
          <li>
            <a href="#" v-on:click="changeMenu('about')">About</a>
          </li>
          <li>
            <a href="#" v-on:click="changeMenu('contact')">Contact</a>
          </li>
        </ul>
      </nav>
    </div>
    <div class="container">
      <keep-alive include="about,contact">
        <component v-bind:is="currentView"></component>
    </keep-alive>
    </div>
  </div>
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

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.header {
  background-color: #ddd;
  padding: 10px 0 0 0;
}
.headerText {
  padding: 0 20px;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #aaa;
}
li {
  float: left;
  padding: 10px;
}
li a {
  display: block;
  color: #000;
  text-align: center;
  padding: 10px;
  text-decoration: none;
}
li a:hover {
  background-color: #aaa;
  color: black;
}
</style>
