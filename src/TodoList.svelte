<script>
  import TodoItem from "./TodoItem.svelte";

  let newTodo;
  let todos = [];

  const addTodo = () => {
    if (newTodo) {
      todos = [...todos, newTodo];
      newTodo = "";
    }
  };

  const handleKeyEnter = (event) => {
    event.code === "Enter" && addTodo();
  };

  const removeTodo = (event) => {
    todos.splice(event.detail, 1);
    todos = todos;
  };

  $: todoLength = todos.length;
</script>

<div class="tl">
  <label for="input-todo">Название дела</label>
  <input
    on:keydown={handleKeyEnter}
    bind:value={newTodo}
    id="input-todo"
    type="text"
    placeholder="Начните печатать..."
  />

  {#each todos as todo, i}
    <TodoItem on:remove={removeTodo} {todo} index={i} />
  {/each}

  <button on:click={addTodo}>Добавить дело</button>
  <span>{todoLength}</span>
</div>

<style>
  .tl {
    display: grid;
    gap: 12px;
    width: 400px;
    margin: auto;
    text-align: left;
  }
</style>
