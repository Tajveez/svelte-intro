<script>
    let todos = [
        { id: 1, text: "Buy Eggs and Sugar.", isDone: false },
        { id: 2, text: "Code your dream project.", isDone: false },
        { id: 3, text: "say buy buy to TM.", isDone: false },
    ];

    // Add new todo
    function add() {
        todos = todos.concat({
            id: todos[todos.length - 1].id + 1,
            text: "",
            isDone: false,
        });
    }

    // Clear Completed todos
    function clear() {
        todos = todos.filter((t) => !t.isDone);
    }

    $: remaining = todos.filter((t) => !t.isDone).length;
</script>

<style>
    .done {
        opacity: 0.5;
    }
    .done input[type="text"] {
        text-decoration: line-through;
    }
</style>

<h1>Todos</h1>
<p>{remaining} remaining</p>
<div>
    <button on:click={add}> Add </button>
    <button on:click={clear}> Clear Completed </button>
</div>
{#each todos as todo}
    <div class:done={todo.isDone}>
        <input
            type="checkbox"
            bind:value={todo.id}
            bind:checked={todo.isDone} />

        <input
            placeholder="What needs to be Done?"
            type="text"
            bind:value={todo.text}
            disabled={todo.isDone ? 'disabled' : ''} />
    </div>
{/each}
