<script>
    import Input from "./Input.svelte";
    import ButtonCounter from "./ButtonCounter.svelte";
    import {Confetti} from 'svelte-confetti';
  import Buttons from "./Buttons.svelte";

    let accept = false;
    let veces = 0;
    let tiemStamps = [];

     function handleConsult(event){

        let {tiemStamp} = event.detail;
        tiemStamps = [...tiemStamps, tiemStamp]

        veces++;
     }
     function handleReset(){
         veces = 0;
         tiemStamps = [];
     }

</script>

<main>

    <Input></Input>

    <label for="">
        <input type="checkbox" bind:checked={accept}/>
            Accept terms and conditions
    </label>

    {#if accept}

        <p>Accepted</p>
         <Confetti />

    {:else }

        <p style="color: red;">No accept</p>

    {/if}

   <Buttons times={veces} on:click={handleConsult} on:reset={handleReset}></Buttons>
    <p>Has been consulted {veces} {veces != 1  ? "Times": "time"}</p>
      {#if veces > 0}
        <p>Last consult: {tiemStamps[tiemStamps.length -1]}</p>
        <p>{veces >= 2 ? "Queries:" : "Consult"}</p>
         <ul>
            {#each tiemStamps as tiemStamp }
              <li>{tiemStamp}</li>
            {/each}
         </ul>
       
      {/if}
      
</main>






