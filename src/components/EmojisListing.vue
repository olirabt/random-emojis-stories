<template>
  <ul class="emojis">
    <li class="emoji" v-for="(emoji, index) in selectedEmojis" :key="emoji+index">{{emoji}}</li>

  </ul>
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
.emojis {
 display: block;
 text-align: center;
 list-style-type: none;

}

.emoji {
  display: inline-block;
  font-size: 22px;
  padding: 3px 6px;
}

</style>
