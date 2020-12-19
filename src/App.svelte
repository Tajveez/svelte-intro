<script>
	import Header from "./components/Header.svelte";
	import Content from "./components/Content.svelte";
	import Counter from "./components/Counter.svelte";
	import Result from "./components/Result.svelte";
	import Cat from "./components/Cat.svelte";

	export let name;
	const character = {
		age: 25,
		profession: "Developer",
	};
	let src = "https://svelte.dev/tutorial/image.gif";
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

<main>
	<Header {name} {...character} />
	<!-- <Header /> -->
	<img {src} alt="Image of {name}" />
	<Content />
	<p>{name} has length of {name.length}</p>
	<Counter />
	<Result />
	<Cat />
</main>
