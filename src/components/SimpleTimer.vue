<!--
https://eugenkiss.github.io/7guis/tasks/#timer
-->

<script>
export default {
  data() {
    return {
      duration: 5 * 1000,
      elapsed: 0
    }
  },
  created() {
    let lastTime = performance.now()
    const update = () => {
      const time = performance.now()
      this.elapsed += Math.min(time - lastTime, this.duration - this.elapsed)
      lastTime = time
      this.handle = requestAnimationFrame(update)
    }
    update()
  },
  unmounted() {
    cancelAnimationFrame(this.handle)
  }
}
</script>

<template>
   <h2>
      <a href="https://vuejs.org/examples/#timer" target="new">
      Timer
      </a>
    </h2> 

  <div>
    Duration: <input type="range" v-model="duration" min="1" max="3000000">
    {{ (duration / 1000).toFixed(1) }}s
  </div>

<label
    >Elapsed Time: <progress :value="elapsed / duration"></progress
  ></label>

  <div>{{ (elapsed / 1000).toFixed(1) }}s</div>


  <button @click="elapsed = 0">Reset</button>
</template>

<style scoped>
.elapsed-container {
  width: 300px;
}

.elapsed-bar {
  background-color: red;
  height: 10px;
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