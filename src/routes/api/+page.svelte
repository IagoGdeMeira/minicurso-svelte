<script lang=ts>
    import { onMount } from "svelte";

    let dados: any;

    onMount(async () => {
        const resposta = await fetch("https://rickandmortyapi.com/api/character");
        dados = await resposta.json();
    })
</script>

<h1>API</h1>

{#if dados}
    <h1>{dados.results[3].name}</h1>
{/if}