<!--
https://eugenkiss.github.io/7guis/tasks/#temp
-->

<script setup>
import { ref } from 'vue'

const c = ref(0)
const f = ref(32)

function setC(e, v = +e.target.value) {
  c.value = v
  f.value = v * (9 / 5) + 32
}

function setF(e, v = +e.target.value) {
  f.value = v
  c.value = (v - 32) * (5 / 9)
}
</script>

<template>
   <h2>
      <a href="https://vuejs.org/examples/#temperature-converter" target="new">
      Temperature Convertor
      </a>
    </h2> 

  <input type="number" :value="c" @change="setC" maxlength="4" size="4"> Celsius = <br> 
  <input type="number" :value="f" @change="setF" maxlength="4" size="4"> Fahrenheit
</template>