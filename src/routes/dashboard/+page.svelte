<script>
	import TodoForm from '../../components/dashboard/TodoForm.svelte';
	import TodoList from '../../components/dashboard/TodoList.svelte';

	// State
	let todoInput = '';

	let todoList = [
		{
			text: 'Buy more milk',
			status: true
		},
		{
			text: 'Buy ramen',
			status: false
		}
	];

	function addToList() {
		todoList = [{ text: todoInput, status: true }, ...todoList];
		todoInput = '';
	}
	function removeFromList(i) {
		todoList.splice(i, 1);
		todoList = todoList;
	}
</script>

<div class="h-screen">
	<div class="flex min-h-full items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
		<div class="w-full max-w-md space-y-16">
			<div>
				<h2 class="mt-6 text-center text-3xl font-bold tracking-tight text-gray-900">
					Welcome to your todo list
				</h2>
			</div>
			<form
				class="mt-8 space-y-6"
				on:submit={(e) => {
					e.preventDefault();
					addToList();
				}}
			>
				<input type="hidden" name="remember" value="true" />
				<div class="-space-y-px rounded-md shadow-sm">
					<div>
						<input
							bind:value={todoInput}
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
			<TodoList todos={todoList} remove={removeFromList} />
		</div>
	</div>
</div>
