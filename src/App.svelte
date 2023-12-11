<script>
    import Input from "./Input.svelte";

    let accept = false;

    export let persons = [
        {name: "John", age: 20},
        {name: "Jane", age: 30},
        {name: "Joe", age: 40},
    ];

</script>


{#each persons as {name, age}}

    <h2>{name}</h2>

    <span>{age}</span>

{/each}

<Input></Input>


<label for="">
<input type="checkbox" bind:checked={accept}/>
    Accept terms and conditions
</label>

{#if accept}
     <p>Accepted</p>
{:else }
    <p style="color: red;">No accept</p>
{/if}
