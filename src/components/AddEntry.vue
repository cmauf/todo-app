<template>
	<div>
		<form @submit="addEntry">
			<input type="text" v-model="text" name="text">
			<button type="submit">RAUF DA!</button>
		</form>
	</div>
</template>

<script>
import uuid from 'uuid';

export default {
	name: 'AddEntry',
	data() {
		return {
			text: ''
			}
		},
	methods: {
		addEntry(e) {
			e.preventDefault();
			
			const newEntry = {
				id: uuid.v4(),
				text: this.text,
				done: false
			}
			
			this.$emit('add-entry', newEntry);
			this.text = '';
		}
	}
}
</script>

<style scoped>
</style>