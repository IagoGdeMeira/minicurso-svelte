<script lang="ts">
    let contador = 0;
</script>

<h1>{contador}</h1>
<button on:click={() => contador++}>+1</button>
<button on:click={() => contador--}>-1</button>