<template>
	<div v-bind:class="{ 'completed': todo.done }">
		<p v-on:click="markComplete">{{ todo.text }}</p>
		<button @click="$emit('delete-todo', todo.id)">WECH!</button>
	</div>
</template>

<script>
	export default {
	name : 'Entry',
	methods: {
		markComplete() {
			this.todo.done = !this.todo.done
		}
	},
	props: [
		"todo"
		]
}

</script>

<style scoped>
	.completed {
		color: #888888;
		text-decoration: underline;
	}
</style>