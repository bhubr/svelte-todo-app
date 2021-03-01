<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();
	export let todo;
</script>

<li class={todo.done ? 'done' : ''}>
  <input id={`cb-${todo.id}`} type="checkbox" checked={todo.done} on:click={() => dispatch('toggleDone')} />
  <label for={`cb-${todo.id}`}>[{todo.id}] {todo.label}</label>
  <button on:click={() => dispatch('delete')}>X</button>
</li>

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