<script lang="ts">
	import type { Data } from "../types";
	import Chart from "./Chart.svelte";
	import Footer from "./Footer.svelte";

	export let data: Data[];
</script>

<section>
	<h3>Spending - Last 7 days</h3>
	<Chart {data} />
	<hr />
	<Footer />
</section>

<style>
	section {
		background-color: #fff;
		border-radius: 16px;
		width: 100%;
		padding: 16px;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}

	hr {
		width: 100%;
		border: 1px solid #e5e5e5;
	}
</style>
