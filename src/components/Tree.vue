<template lang="pug">
  div
    strong {{chart[0].name}} / {{chart[0].type}}
    ul.row
      li.-main(
        v-for="(subs, i) in chart[0].subs"
        v-bind:class="subs.type"
        v-bind:key=i
      ) {{subs.name}}
        ul
          li.-sub(
            v-if="subs.divs"
            v-for="divs in subs.divs"
            v-bind:class="divs.type"
          ) {{divs.name}}
</template>

<script>
export default {
  name: 'tree',
  props: [
    'chart'
  ]
}
</script>

<style lang="sass" scoped>
@import '../assets/common.sass'
.row
  > .-main
    width: 100%
    margin: 10px 0
    text-indent: 10px
    font-weight: bold
    background-color: $primary_color
    > ul
      padding: 10px 10px 20px
      background-color: $white
      > .-sub
        text-indent: 0
        font-weight: normal
        background-color: $white
</style>
