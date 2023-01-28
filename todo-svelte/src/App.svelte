<script>
  let todoItems = []
  let todoInput = ''
  function handleClick(){
    todoItems= [...todoItems, {text: todoInput, checked: false}]
    todoInput = ''
  }
  function handleRemove(index){
   todoItems.splice(index, 1)
    todoItems = todoItems
  }
</script>

<main>
  <div>
    <h1>Todo List</h1><br>
    <input  bind:value= {todoInput}>
    <button  on:click={handleClick}>Add Todo</button>
    <ul> 
      {#each todoItems as item, index}
        <li>
          <input type='checkbox' bind:checked={item.checked}>
            &nbsp {item.text}
            <button on:click={() => handleRemove(index)}>X</button>
        </li>
      {/each} 
    </ul> 
  </div>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
