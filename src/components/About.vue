<template lang="pug">
  div
    h1 About
    h3 {{ (new Date()).toTimeString() }}
    h4 System
    tree(
      v-bind:chart="orgcharts"
    )
</template>
<script>
import Tree from './Tree.vue'
export default {
  name: "about",
  components: {
    Tree
  },
  data: function() {
    return {
      orgcharts : [
        {
          name: "Organization chart",
          type: "company",
          subs: [
            {
              name: "SI division",
              type: "division",
              divs: [
                {
                  name: "SI first",
                  type: "team",
                },
                {
                  name: "SI second",
                  type: "team",
                }
              ]
            },
            {
              name: "BI division",
              type: "division",
              divs: [
                {
                  name: "BI first",
                  type: "team",
                },
                {
                  name: "BI second",
                  type: "team",
                },
                {
                  name: "BI third",
                  type: "team",
                }
              ]
            },
            {
              name: "Solution division",
              type: "division",
              divs: [
                {
                  name: "ESM",
                  type: "team",
                },
                {
                  name: "MTS",
                  type: "team",
                },
                {
                  name: "ASF",
                  type: "team",
                }
              ]
            },
            {
              name: "Head division",
              type: "team"
            },
            {
              name: "Human resource division",
              type: "team"
            }
          ]
        }
      ]
    }
  }
}
</script>
