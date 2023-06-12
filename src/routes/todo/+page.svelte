<script>
  // Simple array of todos
  let todos = [
    { text: "Write my first post", status: true },
    { text: "Upload the post to the blog", status: false },
    { text: "Publish the post at Facebook", status: false },
  ];

  //   Input that gets bound to input field
  let input = "";
  //   Reactive log of the input, logs every time it changes
  // @ts-ignore
  $: console.log(input);

  //   Function to add todos, spread operator is a must to trigger rerender
  const addToTodos = () => {
    todos = [...todos, { text: input, status: false }];
    input = "";
  };

  //   Todos = todos is to trigger rerender, otherwise svelte doesn't know todos changed
  // @ts-ignore
  const removeFromList = (index) => {
    todos.splice(index, 1);
    todos = todos;
  };
</script>

<form on:submit={addToTodos}>
  <input type="text" bind:value={input} />
</form>
<br />

{#each todos as item, index}
  <input bind:checked={item.status} type="checkbox" />
  <span class:checked={item.status}>{item.text}</span>
  <button on:click={() => removeFromList(index)}>❌</button>
  <br />
{/each}

<style>
  .checked {
    text-decoration: line-through;
  }
</style>
