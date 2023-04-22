<script lang="ts">
	import type { Data } from "../types";
</script>

<footer>
	<div class="left">
		<p>Total this month</p>
		<h1>$478.33</h1>
	</div>
	<div class="right">
		<strong>+2.4%</strong>
		<p>from last month</p>
	</div>
</footer>

<style>
	footer {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: flex-end;
		background-color: #fff;
		width: 100%;
	}

	.left {
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		align-items: flex-start;
	}

	.right {
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		align-items: flex-end;
	}

	p {
		font-weight: 400;
		font-size: 10px;
		color: #a9a9a9;
		margin: 0;
	}

	strong {
		font-size: 12px;
	}

	h1 {
		margin: 0;
	}
</style>
