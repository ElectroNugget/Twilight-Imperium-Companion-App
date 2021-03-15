<!-- Main page. App launches from here. Not sure how to route to other components/pages yet. -->
<head>
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>

<script lang="ts">

	import { ListGroup, ListGroupItem, FormGroup, Input, Label } from 'sveltestrap';

	let gameIsStarted = false;

	function startGame () {
		gameIsStarted = true;
	}

	$: console.log('Changed selected:', playerCount)
	$: playerCount=1;

	function doSomething () {

	}

	let playerArray = [
	{
		name:"",
		faction: "",
		colour: "",
	},
	];

	let factionArray = [
		"None",
		"The Arborec",
		"The Brotherhood of Yin",
		"The Barony of Letnev",
		"The Sardakk N'orr",
		"The Embers of Muuat",
		"The Emirates of Hacan",
		"The Ysarril Tribes"
	]

	let colourArray = [
		"None","Red","Blue","Yellow","Green","Black","Purple","Orange","Pink"
	]

</script>

<body>
	{#if !gameIsStarted}
	<main>
		<h1>TWILIGHT IMPERIUM 4th Edition</h1>
		<h3>Companion App</h3>

		<button on:click={startGame}>Start Game</button>
	</main>
	{:else}
	<main>
		<!-- Insert other shit -->
		<p>Hello</p>

		<FormGroup>
			<Label for="exampleSelect">Player Count</Label>
			<!--  svelte-ignore a11y-no-onchange-->
			<select bind:value={playerCount} on:change="{doSomething}">
				<option value={1}>1</option>
				<option value={2}>2</option>
				<option value={4}>4</option>
				<option value={5}>5</option>
				<option value={6}>6</option>
				<option value={7}>7</option>
				<option value={8}>8</option>
			</select>
		</FormGroup>
		
		<ListGroup>
			{#each playerArray as player}
			<ListGroupItem>
				<FormGroup>
					<Label for="exampleEmail">Name</Label>
					<Input plaintext bind:value={player.name}/>
				</FormGroup>
				<FormGroup>
					<Label for="exampleSelect">Faction</Label>
					<select bind:value={player.faction}>
						{#each factionArray as faction}
						<option>{faction}</option>
						{/each}
					</select>
				</FormGroup>
				<FormGroup>
					<Label for="exampleSelect">Colour</Label>
					<select bind:value={player.colour}>
						{#each colourArray as colour}
						<option>{colour}</option>
						{/each}
					</select>
				</FormGroup>
				
				Name: {player.name},
				Faction: {player.faction},
				Colour: {player.colour}
			</ListGroupItem>
			{/each}
		</ListGroup>

	</main>
	{/if}

</body>

<style>
	/* No idea how to make this work. :P */
	/* body {
		background-image: url("../../images/BG_4kSpaceIllus.jpg");
	} */

	select {
		display: inline;
	}
	
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