<script lang=ts>
    import { onMount } from "svelte";
    
    let dados: any;
    let numero: string;

    async function buscarCEP() {
        const resposta = await fetch("https://viacep.com.br/ws/"+ numero +"/json");
        dados = await resposta.json();
        numero = dados;
    }

</script>

<h1>Cep</h1>
<input bind:value={numero} type="text">
<button on:click={() => buscarCEP()} type="button">Enviar</button>

{#if dados}
    <h1>{dados.localidade}</h1>
{/if}
