<script lang="ts">
	import data from "../data.json";
	import "./app.css";
	import Body from "./lib/Body.svelte";
	import Header from "./lib/Header.svelte";
	let balance = new Intl.NumberFormat("en-US", {
		style: "currency",
		currency: "USD",
	}).format(921.48);
</script>

<main class="container">
	<Header {balance} />
	<Body {data} />
</main>

<style>
	.container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		min-width: 300px;
		gap: 16px;
	}
</style>
