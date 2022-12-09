<script>
	export let todos;
	export let remove;
</script>

<div class="rounded-lg shadow-lg p-8 flex flex-col gap-4">
	{#each todos as item, index}
		<div class="rounded-md p-4 justify-between flex flex-row border-2 border-gray-800">
			<div class="font-medium text-sm">{item.text}</div>
			<button on:click={() => remove(index)}>x</button>
		</div>
	{/each}
</div>
