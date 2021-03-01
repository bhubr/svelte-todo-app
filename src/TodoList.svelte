<script>
	import Todo from './Todo.svelte';
	let items = [
    { id: 1, label: 'item 1', done: false },
    { id: 2, label: 'item 2', done: true },
    { id: 3, label: 'item 3', done: false },
  ];
  $: uncompletedCount = items.filter(it => !it.done).length
  $: status = `${uncompletedCount} of ${items.length} remaining`

  const toggleDone = (todoId) => {
    items = items.map(t => t.id !== todoId ? t : { ...t, done: !t.done });
  }

  const deleteTodo = (todoId) => {
    items = items.filter(t => t.id !== todoId);
  }
</script>

<section>
  <h3>Current items</h3>
  {status}
  <ul>
  {#each items as todo}
    <Todo todo={todo} on:delete={() => deleteTodo(todo.id)} on:toggleDone={() => toggleDone(todo.id)} />
  {/each}
  </ul>
</section>

<style>
  li {
    list-style-type: none;
  }
  li.done {
    text-decoration: line-through;
    color: #777;
  }
  label {
    display: inline;
  }
</style>