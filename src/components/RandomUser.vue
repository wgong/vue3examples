<template>
<!-- 
    https://codepen.io/bradtraversy/pen/LYbzJjK
-->
   <h2>
      <a href="https://codepen.io/bradtraversy/pen/LYbzJjK" target="new">
        Random User Generator
      </a>
    </h2> 
    by <a href=https://github.com/bradtraversy target="new">Brad Traversy</a>
    <div id="app">
        <img
          v-bind:src="picture"
          :alt="`${firstName} ${lastName}`"
          :class="gender"
            width="250" height="250"
        />
        <h1>{{firstName}} {{lastName}}</h1>
        <h3>Email: {{email}}</h3>
        <button :class="gender" @click="getUser()">Get Random User</button>
      </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: 'John',
      lastName: 'Doe',
      email: 'john@gmail.com',
      gender: 'male',
      picture: 'https://randomuser.me/api/portraits/men/10.jpg',
    }
  },
  methods: {
    async getUser() {
      const res = await fetch('https://randomuser.me/api')
      const { results } = await res.json()

      // console.log(results)

      this.firstName = results[0].name.first
      this.lastName = results[0].name.last
      this.email = results[0].email
      this.gender = results[0].gender
      this.picture = results[0].picture.large
    },
  },
}

</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html,
body {
  font-family: Arial, Helvetica, sans-serif;
}

#app {
  width: 400px;
  height: 100vh;
  margin: auto;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1,
h3 {
  margin-bottom: 1rem;
  font-weight: normal;
}

img {
  border-radius: 50%;
  border: 5px #333 solid;
  margin-bottom: 1rem;
}

.male {
  border-color: steelblue;
  background-color: steelblue;
}

.female {
  border-color: pink;
  background-color: pink;
  color: #333;
}

button {
  cursor: pointer;
  display: inline-block;
  background: #333;
  color: white;
  font-size: 18px;
  border: 0;
  padding: 1rem 1.5rem;
}

button:focus {
  outline: none;
}

button:hover {
  transform: scale(0.98);
}

</style>