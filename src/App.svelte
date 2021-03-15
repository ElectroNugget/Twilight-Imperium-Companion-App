<!-- Main page. App launches from here. Not sure how to route to other components/pages yet. -->

<script>
	// This is how you import a component. :P
	import Navbar from "./Navbar.svelte"
</script>

<Navbar/>

<body>
	<main>
		<h1>TWILIGHT IMPERIUM 4th Edition</h1>
		<h3>Companion App</h3>

		<button href="/GameSetup">Start Game</button>
		<!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
	</main>
</body>

<style>
	/* No idea how to make this work. :P */
	/* body {
		background-image: url("../../images/BG_4kSpaceIllus.jpg");
	} */
	
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
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