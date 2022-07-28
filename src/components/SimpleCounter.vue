<!--
https://eugenkiss.github.io/7guis/tasks/#counter
-->

<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
   <h2>
      <a href="https://vuejs.org/examples/#counter" target="new">
      Counter
      </a>
    </h2> 

  <h2 style="text-align:left;">
    {{ count }} 
  </h2>
  <button @click="count++">Count</button> 
  <button @click="count=0;">Reset</button>
</template>


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