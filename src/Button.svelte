<script>
   export let name;
   
    function handleClick() {
        alert(`Hello ${name}!`);
    }

    function handleState(name) {

        if (name === undefined || name === null || name === "") {

            return true;

        } 

     return false;

    }

</script>

<button disabled={handleState(name)} 
 on:click={ handleClick }>
    click me!
</button>
