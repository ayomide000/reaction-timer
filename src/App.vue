<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click='start' :disabled="isPlaying">play</button>
  <BlockGame v-if='isPlaying' :delay='delay' />
</template>

<script>
  import BlockGame from './components/BlockGame.vue'

export default {
  name: 'App',
  components: {BlockGame},
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      // console.log(this.delay);
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
