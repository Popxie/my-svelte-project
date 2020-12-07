<script>
	import Basic from './Basic.svelte'
	import Info from './Info.svelte'
	import Each from './Each.svelte'
	import Event from './Event.svelte'
	import Store from './Store/Store.svelte'

	const pkg = {
		name: 'svelte',
		version: 3,
		age: 22,
		speed: 'blazing',
		website: 'https://svelte.dev'
	}
	function sayHello(event) {
		const { detail: { text } } = event
		console.log('event: ', event)
		alert(text)

	}
</script>

<main>
	<h1>Hello {$$props.name}!</h1>
	<h3>{JSON.stringify(pkg)}</h3>
	<Basic />
	<hr>
	<Info {...pkg}/>
	<hr>
	<Each />
	<hr>
	<Event on:message={sayHello}/>
	<hr>
	<Store />
</main>

<style>
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