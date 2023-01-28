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
    <input type='text' bind:value= {todoInput}>
    <button  on:click={handleClick}>Add Todo</button>
    <ul> 
      {#each todoItems as item, index}
        <li>
          <input type='checkbox' bind:checked={item.checked}>
             <span class:checked={item.checked}>{item.text}</span>
            <button class= 'removeBtn' on:click={() => handleRemove(index)}>X</button>
        </li>
      {/each} 
    </ul> 
  </div>
</main>

<style>
 .checked{
   text-decoration: line-through;
 } 
 input[type='text']{
   height: 30px;
   width: 200px;
   margin: 20px;
 }
 li{
  text-align: left;
   height: 42px;
  }
 .removeBtn{
   float: right;
 }
 span{
   margin-left: 25px;
   font-size: 24px;
 }
 input[type='checkbox']{
   transform: scale(2.5);
 }
</style>
