<template>
  <div id="app">
	<AddEntry v-on:add-entry="addEntry" v-on:delete-todo="deleteEntry" />
	<Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Todos from './components/Todos';
import AddEntry from './components/AddEntry';

export default {
  name: 'app',
  components: {
	Todos,
	AddEntry
	},
  data() {
	return {
		todos: [
			{ id: 1, text: 'mach das feddich', done: false},
			{ id: 2, text: 'aber wirds bald?', done: false},
			{ id: 3, text: 'und dann ab ins bett!', done: false}
			]
		}
	},
	methods: {
		addEntry(newEntry) {
			this.todos = [...this.todos, newEntry];
		},
		deleteEntry(entryId) {
			this.todos = this.todos.filter(todo => todo.id !== entryId);
		}
	}
}
</script>

<style>

</style>
