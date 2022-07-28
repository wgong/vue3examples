<!--
This example demonstrates handling user input with the v-on directive.
-->

<script>
export default {
  // props: {
  //   title: String,
  //   url: String
  // },    
  data() {
    return {
      title: "Handling User Input",
      url: "https://vuejs.org/examples/#handling-input",
      message: 'Welcome to Vue world',
      comment: "Awesome Vue JS"
    }
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split('').reverse().join('')
    },
    notify() {
      alert('navigation was prevented.')
    }
  }
}
</script>

<template>
  <!--
    Note we don't need .value inside templates because
    refs are automatically "unwrapped" in templates.
  -->
   <h2>
      <a :href="url" target="new">{{title}}</a>
    </h2> 

<div>
    <label for="short_text">
        Enter a short message: 
    </label>
    <input
      type="text"
      id="short_text"
      name="short-text"
      autocomplete="off"
      v-model.lazy.trim="message"
    />

<!--
    Bind to a method/function.
    The @click syntax is short for v-on:click.
  -->
</div>
    <button @click="reverseMessage">Reverse Message</button>


<div>
      <label for="long_text">
        Leave a long comment: 
    </label>
    <textarea 
        id="long_text" 
        name="long-text"
        autocomplete="off"
        v-model.lazy.trim="comment">
    </textarea>



</div>
  <!-- Can also be an inline expression statement -->
  <button @click="comment += '!'">Append "!"</button>

<div>
  Update Titile Link URL:
<input type="text" v-model="url" size="60">
</div>


  <!--
    Vue also provides modifiers for common tasks
    such as e.preventDefault() and e.stopPropagation()
  -->
  <a href="https://vuejs.org" @click.prevent="notify">
    A link with e.preventDefault()
  </a>
</template>



<style scoped>
a {
  display: block;
  margin-bottom: 1em;
  
}

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