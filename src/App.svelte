<script lang="typescript">
	export let name: string;
	// TODO: disable ts(1192) warning in workspace
	// @ts-ignore
	import TopAppBar from './components/TopAppBar.svelte';
	// @ts-ignore
	import NavSideBar from './components/NavSideBar.svelte';

	let showSideBar = false;

	const toggleNav = () => {
		showSideBar = !showSideBar;
	}

	
</script>

<!-- TODO: Refactor this into a layout component -->
<TopAppBar on:toggleNav={toggleNav}/>
<NavSideBar bind:show={showSideBar}/>
<div class="mdc-drawer-app-content mdc-top-app-bar--fixed-adjust">
	<main>
		<h1>Hello {name}!</h1>
		<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	</main>
</div>

<style lang="scss">
	$main-color: #ff3e00;

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: $main-color;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>