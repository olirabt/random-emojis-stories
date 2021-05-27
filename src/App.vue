<template>
  <div class="container">
    <Button label="Générer une histoire !" @button-was-clicked="refreshKey++" />
    <EmojisListing :key="refreshKey"/>
    <TextField @update-story="refreshStory" />
  </div>
</template>

<script>
import EmojisListing from './components/EmojisListing.vue'
import Button from './components/Button.vue'
import TextField from './components/TextField.vue'


export default {
  name: 'App',
  components: {
    EmojisListing,
    Button,
    TextField
  },
  methods: {
    refreshStory(val) {
      this.enterredStory = val;
    },
 
  },
  data() {
    return {
      refreshKey: 0,
      enterredStory: ''
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
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  display: block;
  max-width: 60vw;
  margin: 2rem auto;
}
</style>
