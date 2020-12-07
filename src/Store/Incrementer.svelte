<script>
import { count } from "./stores.js";
  function increment() {
    count.update( count => count + 1)
  }
</script>

<button on:click="{increment}"> + </button>