<script>
	import TodoList from './TodoList.svelte';
</script>

<main>
	<h1>Svelte TodoApp</h1>
	<h2>First steps outside the REPL</h2>
	<TodoList />
</main>

<style>
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	h1, h2 {
		text-align: center;
	}

	h2 {
		font-weight: 200;
	}

	@media (min-width: 640px) {
		main {
			max-width: 720px;
		}
	}
</style>