<template>
  <div class="container">
    <Button label="Générer une histoire !" @button-was-clicked="refreshKey++" />
    <EmojisListing :key="refreshKey"/>
    <TextField @update-story="refreshStory" />
    <div class="toast" v-bind:class="{ visible: showToast }">Le texte a été copié !</div>  <!-- todo: component + transition clean parce que là c'est pas ouf -->
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
  data() {
    return {
      refreshKey: 0,
      enterredStory: '',
      showToast: false
    }
  },
  methods: {
    refreshStory(val) {
      this.showToast = true;
      this.enterredStory = val;
      setTimeout(() => this.showToast = false, 4000);
    },
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

.toast {
  display: block;
  opacity: 0;
  position: absolute;
  top: 0;
  right: 0;
  padding: 10px;
  border-bottom-left-radius: 5px;
  text-align: center;
  background: chartreuse;
  transition: opacity .3s ease-out;
}

.visible {
  opacity: 1;
}
</style>
