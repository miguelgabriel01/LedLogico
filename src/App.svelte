<script>
	import Router from "svelte-spa-router"; //importamos a dependencia de rotas
	import Inicio from "../src/components/Inicio.svelte"; //fazemos a importação do componente Inicio.svelte

	import Menu from "../src/components/Menu.svelte"; //importamos o componente menu
	import Sobre from "../src/components/Sobre.svelte"//importamos o componente sobre
	import Perdeu from "../src/components/Perdeu.svelte"//importamos o componente Perdeu
	import Venceu from "../src/components/Venceu.svelte"//importamos o componente Venceu
	import Personagem from "../src/components/Personagem.svelte"//importamos o componente Personagem
	import Desistente from "../src/components/Desistente.svelte"//importamos o componente Desistente

	const routes = {
		"/": Menu,
		"/jogar": Inicio,
		"/sobre": Sobre,
		"/perdeu": Perdeu,
		"/venceu": Venceu,
		"/heroi": Personagem,
		"/desistir": Desistente
	};
</script>

<main>
	<Router {routes} />
</main>

<style>
</style>
