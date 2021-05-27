<template>
  <button @click="onClick">
		{{ label }}
	</button>
</template>

<script>

export default {
  name: 'Button',
	props: {
		label: {
			type: String,
		},
	},
  
  methods: {
    onClick() {
			this.$emit('button-was-clicked');
		}
  },

}

</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}

</style>
