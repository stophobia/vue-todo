<template>
  <ul class="row">
    <li v-for="sub in subs" v-bind:class="sub.type">
      {{sub.name}}
      <tree v-bind:subs="sub.subs"></tree>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'tree',
  props: [
  'subs'
  ]
}
</script>
<style scoped>
ul.row li {
  background-color: transparent !important;
}
</style>