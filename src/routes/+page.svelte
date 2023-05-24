<script>
	import Cagr from './Cagr.svelte';
</script>

<svelte:head>
	<title>Simple CAGR Calculator</title>
	<meta name="description" content="Calculate you some CAGR" />
</svelte:head>

<section>
	<h3>
	  Calculate you some CAGR:
	</h3>
	<Cagr />
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		align-items: center;
		flex: 0.6;
		padding-top:30px;
	}

	h3 {
		width: 100%;
		text-align:center;
		margin:0;
	}
</style>
