<!--
Here we are reactively binding element attributes / properties to the state.
The :title syntax is short for v-bind:title.
-->



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
    This should be green, and should toggle between green and blue on click.
  </p>
</template>

<script>
export default {
  props: {
    title: String
  },      
  data() {
    return {
      message: "Learn Attribute Binding",  
      isRed: true,
      color: 'green'
    }
  },
  methods: {
    toggleRed() {
      this.isRed = !this.isRed
    },
    toggleColor() {
      this.color = this.color === 'green' ? 'blue' : 'green'
    }
  }
}
</script>

<style scoped>
.red {
  color: red;
}
</style>