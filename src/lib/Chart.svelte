<script lang="ts">
	import type { Data } from "../types";
	import Tooltip from "./Tooltip.svelte";

	export let data: Data[];
	let activeDays: string[] = [];
	const currentWeekDay = new Date()
		.toLocaleString("en-US", { weekday: "short" })
		.toLowerCase();

	// Find the day with the highest amount
	$: max = data.reduce((acc, { amount, day }) => {
		if (amount > acc) {
			return amount;
		}
		return acc;
	}, 0);

	// Calculate the percentage of each day (will be used to set the height of the bar)
	$: parsed = data.map((d) => ({
		...d,
		percent: Math.round((d.amount / max) * 100),
	}));

	function toggleActiveDay(day: string) {
		const isActive = activeDays.includes(day);
		if (isActive) {
			activeDays = activeDays.filter((d) => d !== day);
		} else {
			activeDays = [...activeDays, day];
		}
	}
</script>

<section class="chart-container">
	{#each parsed as { day, percent, amount }, i}
		<div class="chart-item">
			<button
				on:mouseenter={() => toggleActiveDay(day)}
				on:mouseleave={() => toggleActiveDay(day)}
				class="chart-item__bar"
				class:current={day === currentWeekDay}
				class:active={activeDays.includes(day)}
				style="height: {percent}%"
				tabindex={i + 1}
			>
				<Tooltip text={amount} show={activeDays.includes(day)} />
			</button>
			<h5>{day}</h5>
		</div>
	{/each}
</section>

<style>
	.chart-container {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: flex-start;
		width: 100%;
		height: 250px;
		gap: 8px;
		padding-top: 24px;
	}

	.chart-item {
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		align-items: center;
		width: 100%;
		height: 100%;
	}

	.chart-item__bar {
		position: relative;
		cursor: pointer;
		width: 100%;
		background-color: var(--color-primary-red);
		border-radius: 8px;
		border-width: 0;
	}

	.chart-item__bar.current {
		background-color: var(--color-primary-cyan);
	}

	.chart-item__bar.active {
		filter: brightness(1.2);
	}

	h5 {
		font-size: 10px;
		font-style: normal;
		font-weight: 400;
		margin-bottom: 8px;
	}
</style>
