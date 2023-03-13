<script lang="ts">
    import Todo from "../lib/Todo.svelte";
    let todos = ["Rydde", "hallo"]
    let add_item: string = "";
    function add(x: string) {
        todos.push(x)
        todos = todos;
    }
    function remove(x: number) {
        todos.splice(x, 1)
        todos = todos;
    }
</script>


<h1>Todos</h1>
<input bind:value={add_item}>
<button on:click={() => add(add_item)}>Add todo</button>


{#each todos as todo, i}
<br/>
    <button on:click={() => remove(i)}>Delete {todo}</button>
    <Todo name={todo} />
{/each}