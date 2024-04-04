<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  const removeTodo = () => {
    dispatch("remove", index);
  };

  export let todo;
  export let index;
</script>

<div class="ti">
  <span>{index + 1}: {todo}</span>
  <span on:click={removeTodo} class="ti__btn_remove">Удалить</span>
</div>

<style>
  .ti {
    display: inline-flex;
    justify-content: space-between;
    padding: 8px;
    border-radius: 4px;
    background-color: steelblue;
    color: white;
  }

  .ti__btn_remove {
    color: red;
    cursor: pointer;
  }

  .ti__btn_remove:hover {
    color: darkred;
  }
</style>
