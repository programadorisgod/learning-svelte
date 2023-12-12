<script>
  import {createEventDispatcher} from "svelte"
  import ButtonCounter from "./ButtonCounter.svelte";

   export let times;
   
   let dispatch = createEventDispatcher()

    function handleReset(){
        dispatch("reset")
    }

    function handleButton(times) {
        if (times < 1) return true

        return false
    }

</script>


<ButtonCounter on:click/>
<button disabled={handleButton(times)} on:click={handleReset}>Reset</button>