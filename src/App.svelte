<script>
  import TodoList from "./TodoList.svelte";
  let name = "world";
</script>

<main>
  <h1>Hello {name}!</h1>
  <TodoList />
</main>

<style>
  main {
    text-align: center;
    padding: 10px;
    max-width: 300px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
</style>
