<!--
https://eugenkiss.github.io/7guis/tasks/#crud
-->

<script>
export default {
  data() {
    return {
      names: ['Emil, Hans', 'Mustermann, Max', 'Tisch, Roman'],
      selected: '',
      prefix: '',
      first: '',
      last: ''
    }
  },
  computed: {
    filteredNames() {
      return this.names.filter((n) =>
        n.toLowerCase().startsWith(this.prefix.toLowerCase())
      )
    }
  },
  watch: {
    selected(name) {
      [this.last, this.first] = name.split(', ')
    }
  },
  methods: {
    create() {
      if (this.hasValidInput()) {
        const fullName = `${this.last}, ${this.first}`
        if (!this.names.includes(fullName)) {
          this.names.push(fullName)
          this.first = this.last = ''
        }
      }
    },
    update() {
      if (this.hasValidInput() && this.selected) {
        const i = this.names.indexOf(this.selected)
        this.names[i] = this.selected = `${this.last}, ${this.first}`
      }
    },
    del() {
      if (this.selected) {
        const i = this.names.indexOf(this.selected)
        this.names.splice(i, 1)
        this.selected = this.first = this.last = ''
      }
    },
    hasValidInput() {
      return this.first.trim() && this.last.trim()
    }
  }
}
</script>

<template>

   <h2>
      <a href="https://vuejs.org/examples/#crud" target="new">
      CRUD
      </a>
    </h2> 

  <div><input v-model="prefix" placeholder="Filter prefix"></div>

  <select size="5" v-model="selected">
    <option v-for="name in filteredNames" :key="name.indexOf">{{ name }}</option>
  </select>

  <label>First Name: <input v-model="first"></label>
  <label>Last Name: <input v-model="last"></label>

  <div class="buttons">
    <button @click="create">Create</button>
    <button @click="update">Update</button>
    <button @click="del">Delete</button>
  </div>
</template>

<style scoped>
* {
  font-size: inherit;
}

input {
  display: block;
  margin-bottom: 10px;
}

select {
  float: left;
  margin: 0 1em 1em 0;
  width: 14em;
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