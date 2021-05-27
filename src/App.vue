<template>
  <Button label="Générer une histoire !" @button-was-clicked="refreshStory" />
  <EmojisListing :key="refreshKey"/>
</template>

<script>
import EmojisListing from './components/EmojisListing.vue'
import Button from './components/Button.vue'


export default {
  name: 'App',
  components: {
    EmojisListing,
    Button
  },
  methods: {
    refreshStory() {
      this.refreshKey++;
    }
  },
  data() {
    return {
      refreshKey: 0
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
</style>
