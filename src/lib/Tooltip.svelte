<script lang="ts">
	export let text: string | number;
	export let show = false;
</script>

<p class:fade-in={show}>
	{text}
</p>

<style>
	p {
		position: absolute;
		top: -30px;
		font-size: 12px;
		left: 50%;
		transform: translateX(-50%);
		background-color: #000;
		color: #fff;
		border-radius: 8px;
		margin: 0;
		padding: 4px 8px;
		transition: 0.5s ease-in-out;
		opacity: 0;
		font-weight: 700;
	}

	p::after {
		content: "";
		position: absolute;
		top: 100%;
		left: 50%;
		transform: translateX(-50%);
		border: 8px solid transparent;
		border-top-color: #000;
	}

	p.fade-in {
		opacity: 1;
	}
</style>
