<template>
  <div class="hello">
    <p>{{selectedEmojis}}</p>
  </div>
</template>

<script>
import emojiCompact from  './../emoji-compact.json'; // emoji.json

export default {
  name: 'EmojisListing',
  data: () => {
    return {
      minRange: 20,
      maxRange: 30,
      selectedEmojis: []
    }
  },
  computed: {
    numberOfEmojis: function() {
      return emojiCompact.length
    }
  },
  methods: {
    generateRange(min, max) {
       return Math.floor(Math.random() * max) + min
    },
    generateEmojisList() {
      const howManyEmojis = this.generateRange(this.minRange, this.maxRange);
      const numberOfEmojis = emojiCompact.length;
      

      for (let index = 0; index < howManyEmojis; index++) {

        this.selectedEmojis.push(emojiCompact[this.generateRange(0, numberOfEmojis)]);
      }

      return;
    }
  },
  mounted: function () {
    this.generateEmojisList()
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
