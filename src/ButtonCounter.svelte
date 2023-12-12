<script>
  import {createEventDispatcher} from "svelte"
  let dispatch = createEventDispatcher()

  function handleClick() {
        let date = new Date()
        
        dispatch("click", {
            tiemStamp: date.toLocaleTimeString()
        })
   }

</script>

<button on:click={handleClick}>
    click me for counter!
</button>