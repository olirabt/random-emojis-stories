<template>
<div>
	<textarea v-model="content" placeholder="Écrivez une histoire" rows="6"></textarea>
	<button @click="validateStory">Valider cette histoire</button>  <!-- //todo: resuse Button -->
</div>
  
</template>

<script>

export default {
  name: 'TextField',
	data() {
		return {
			content: '',
		}
	},
	methods: {
		validateStory() {
			this.$emit('update-story', this.content);
		},
	},

}

</script>

<style scoped>
textarea {
	width: 100%;
	padding: 8px;
	border: 1px solid black;
	border-radius: 3px;
	line-height: 18px;
}

</style>
