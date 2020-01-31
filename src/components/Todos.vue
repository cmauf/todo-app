<template>
	<div>
		<h2>To Do For You</h2>
		<ul>
			<li v-bind:key="todo.id" v-for="todo in todos">
				<Entry v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
			</li>
		</ul>
	</div>
	
</template>

<script>
	import Entry from './Entry';
	
	export default {
		name: 'Todos',
		components: {
			Entry
		},
		props: [
			"todos"
			]
	}
</script>

<style scoped>
</style>
