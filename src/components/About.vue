<template>
  <div>
    <h1>About</h1>
    <h3>{{ (new Date()).toTimeString() }}</h3>
    <h4>System</h4>
    <tree v-bind:subs="orgcharts"></tree>
  </div>
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
          name: "Todolist",
          type: "company",
          subs: [
            {
              name: "SI division",
              type: "division",
              subs: [
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
              subs: [
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
              subs: [
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