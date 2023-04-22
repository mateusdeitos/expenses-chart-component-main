<script lang="ts">
	export let balance: string;
</script>

<header>
	<section>
		<h5>My balance</h5>
		<p>{balance}</p>
	</section>
	<img src="./images/logo.svg" alt="" />
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: var(--color-primary-red);
		width: 100%;
		padding: 24px;
		border-radius: 16px;
	}

	section {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: flex-start;
	}

	img {
		width: 48px;
	}

	p,
	h5 {
		color: white;
		margin: 0;
	}

	h5 {
		font-size: 10px;
		font-style: normal;
		font-weight: 400;
		margin-bottom: 8px;
	}
</style>
