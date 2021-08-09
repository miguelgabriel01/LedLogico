<script>
	import Router from "svelte-spa-router"; //importamos a dependencia de rotas
	import Inicio from "../src/components/Inicio.svelte"; //fazemos a importação do componente Inicio.svelte

	import Menu from "../src/components/Menu.svelte"; //importamos o componente menu
	import Sobre from "../src/components/Sobre.svelte"//importamos o componente sobre

	const routes = {
		"/": Menu,
		"/jogar": Inicio,
		"/sobre": Sobre
	};
</script>

<main>
	<Router {routes} />
</main>

<style>
</style>
