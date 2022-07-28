<!--
Here we are reactively binding element attributes / properties to the state.
The :title syntax is short for v-bind:title.
-->
<script setup>
import { ref } from 'vue'

const message = ref('Hello World!')
const isRed = ref(true)
const color = ref('lime')

function toggleRed() {
  isRed.value = !isRed.value
}

function toggleColor() {
  color.value = color.value === 'lime' ? 'blue' : 'lime'
}
</script>


<template>
   <h2>
      <a href="https://vuejs.org/examples/#attribute-bindings" target="new">
        Attribute Binding
      </a>
    </h2> 
  <p>
    <span :title="message">
      Hover your mouse over me for a few seconds to see my dynamically bound title!
    </span>
  </p>

  <!--
  class bindings have special support for objects and arrays
  in addition to plain strings
  -->
  <p :class="{ red: isRed }" @click="toggleRed">
    This should be red... but click me to toggle it.
  </p>

  <!-- style bindings also support object and arrays -->
  <p :style="{ color }" @click="toggleColor">
    This should be lime, and should toggle between lime and blue on click.
  </p>
</template>



<style scoped>
.red {
  color: red;
}
</style>