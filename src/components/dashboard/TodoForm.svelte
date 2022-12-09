<script>
	export let todoInput;
	export let add;
</script>

<div>
	<h2 class="mt-6 text-center text-3xl font-bold tracking-tight text-gray-900">
		Welcome to your todo list
	</h2>
</div>
<form
	class="mt-8 space-y-6"
	on:submit={(e) => {
		e.preventDefault();
		add();
	}}
>
	<input type="hidden" name="remember" value="true" />
	<div class="-space-y-px rounded-md shadow-sm">
		<div>
			<label for="todo-input" class="sr-only">Email address</label>
			<input
				bind:value={todoInput}
				id="todo-input"
				name="todo-input"
				type="text"
				class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-indigo-500 focus:outline-none focus:ring-indigo-500 sm:text-sm"
				placeholder="Enter a todo"
			/>
		</div>
	</div>

	<div>
		<button
			type="submit"
			class="group relative flex w-full justify-center rounded-md border border-transparent bg-indigo-600 py-2 px-4 text-sm font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
		>
			Add todo
		</button>
	</div>
</form>
