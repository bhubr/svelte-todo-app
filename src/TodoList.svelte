<script>
	export let items = [
    { id: 1, label: 'item 1', done: false },
    { id: 2, label: 'item 2', done: true },
    { id: 3, label: 'item 3', done: false },
  ];
</script>

<section>
  <h3>Current items</h3>
  <ul>
  {#each items as item}
    <li class={item.done ? 'done' : ''}>
      <input id={`cb-${item.id}`} type="checkbox" bind:checked={item.done} />
      <label for={`cb-${item.id}`}>[{item.id}] {item.label}</label>
    </li>
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