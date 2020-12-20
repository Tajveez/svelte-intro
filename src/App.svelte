<script>
	import Header from "./components/Header.svelte";
	import Content from "./components/Content.svelte";
	import Counter from "./components/Counter.svelte";
	import Result from "./components/Result.svelte";
	import Cat from "./components/Cat.svelte";
	import DomEvents from "./components/DomEvents.svelte";
	import PromiseCode from "./components/PromiseCode.svelte";

	export let name;
	const character = {
		age: 25,
		profession: "Developer",
	};
	let src = "https://svelte.dev/tutorial/image.gif";

	// for dimensions
	let m = { x: 0, y: 0 };
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	p {
		color: green;
		font-family: "Comic Sans MS", cursive;
		font-size: 2em;
	}
</style>

<main on:mousemove={(e) => (m = { x: e.clientX, y: e.clientY })}>
	<DomEvents />
	<div>Main mouse movement records: x: {m.x} and y: {m.y}</div>
	<Header {name} {...character} />
	<!-- <Header /> -->
	<img {src} alt="Image of {name}" />
	<Content />
	<p>{name} has length of {name.length}</p>
	<Counter />
	<Result />
	<Cat />
	<PromiseCode />
</main>
