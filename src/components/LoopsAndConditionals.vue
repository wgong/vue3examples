<!--
We can render content conditionally or in a loop with the v-if and v-for directives.
-->
<template>
   <h2>
      <a href="https://vuejs.org/examples/#conditionals-and-loops" target="new">
      Conditionals and Loops
      </a>
    </h2> 

  <button @click="show = !show">Toggle List</button>
  <button @click="list.push(addNumber(list))">Push Number</button>
  <button @click="list.pop()">Pop Number</button>
  <button @click="list.reverse()">Reverse List</button>
  <button @click="list.sort()">Sort List</button>

  <ul v-if="show && list.length">
    <li v-for="item of list" :key="item.indexOf">{{ item }}</li>
  </ul>
  <p v-else-if="list.length">List is shown as string: {{list.join(',')}}.</p>
  <p v-else>List is empty.</p>
</template>

<script>
export default {

    data() {
        return {
            show: true,
            list: [],
            refurl: "https://vuejs.org/examples/#conditionals-and-loops"
        }
    },
    methods: {
      addNumber(arr) {
        if (arr.length) {
          //https://stackoverflow.com/questions/1669190/find-the-min-max-element-of-an-array-in-javascript/1669222#1669222
          return Math.max(...arr)+1
        } else {
          return 1
        }
      }
    }
}
</script>

<style scoped>
button {
  cursor: pointer;
  display: inline-block;
  background: rgb(122, 190, 221);
  color: rgb(27, 22, 22);
  font-size: 12px;
  border: 2px;
  padding: 0.5rem 0.5rem;
  margin: 5px;
}
</style>


