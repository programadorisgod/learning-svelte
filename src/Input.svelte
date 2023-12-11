<script>
 import Button from "./Button.svelte";

 let name;

 function handleInput(event){
    name = event.target.value;
 }

</script>

<input type="text" placeholder="Type your name here" on:change={handleInput} >

{#if !name }
    <p>Enter your name:</p>
{/if}

<Button name={name}></Button>
