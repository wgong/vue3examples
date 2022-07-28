<!--
We can create two-way bindings between state and form inputs using the v-model directive.
-->

<script>
export default {
  data() {
    return {
      text: 'Edit me',
      checked: true,
      checkedNames: ['Jack'],
      picked: 'One',
      selected: 'A',
      multiSelected: ['A']
    }
  }
}
</script>

<template>

   <h2>
      <a href="https://vuejs.org/examples/#form-bindings" target="new">
        Form bindings
      </a>
    </h2> 

  <h3>Text Input</h3>
  <input v-model="text"> <br>{{ text }}

  <h3>Checkbox</h3>
  <input type="checkbox" id="checkbox" v-model="checked">
  <label for="checkbox">Checked: {{ checked }}</label>

  <!--
    multiple checkboxes can bind to the same
    array v-model value
  -->
  <h3>Multi Checkbox</h3>
  <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
  <label for="jack">Jack</label>
  <input type="checkbox" id="john" value="John" v-model="checkedNames">
  <label for="john">John</label>
  <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
  <label for="mike">Mike</label>
  <p>Checked names: <pre>{{ checkedNames }}</pre></p>

  <h3>Radio</h3>
  <input type="radio" id="one" value="One" v-model="picked">
  <label for="one">One</label>
  <br>
  <input type="radio" id="two" value="Two" v-model="picked">
  <label for="two">Two</label>
  <br>
  <span>Picked: {{ picked }}</span>

  <h3>Select</h3>
  <select v-model="selected">
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ selected }}</span>

  <h3>Multi Select</h3>
  <select v-model="multiSelected" multiple style="width:100px">
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ multiSelected }}</span>
</template>