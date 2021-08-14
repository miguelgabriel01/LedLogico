<script>
    import { onMount,onDestroy } from "svelte";
    let clearSetTimeout = '';

    
    onMount(async () => {
        await handleRedirecionamento();
    });

    function handleRedirecionamento() {
        // your script goes here
       clearSetTimeout = setTimeout(function () {
            window.location.href = "#/";
        }, 8000); //x segundos
    }

    onDestroy(() => {
        clearTimeout(clearSetTimeout);
    });
</script>

<section class="venceu">
    <h1 class="mensagem">você falhou com seu povo</h1>
    <div class="poderesOPPerdeu">
        <div class="poderOP1Perdeu" />
        <div class="poderOP2Perdeu" />
        <div class="poderOP3Perdeu" />
        <div class="poderOP4Perdeu" />
        <div class="poderOP5Perdeu" />
    </div>
    <a class="buttonContinuarVenceu" href="#/" style="background:red">Menu</a>
</section>
