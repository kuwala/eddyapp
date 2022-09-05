<script lang="ts">
	import Counter from '$lib/Counter.svelte';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Eddy Eddy Eddy's group page" />
</svelte:head>

<section class="xp-desktop">
	<p> Eddy Eddy Eddy</p>
	<p> Eddy Eddy Eddy</p>
	<p> Eddy Eddy Eddy</p>
	<p> <a href="archive/2019/index.html">Check out the archive</a></p>
	<img class="xp-img" src="img/bliss-2006.jpeg" alt="location from windows xp bliss wallpaper in 2006.">

</section>

<style>
	.xp-img {
		width: 900px;
		border-radius: 4px;
	}
	.xp-img:hover {
		box-shadow: 0 0 8px 4px rgba(0, 140, 186, 0.5);
	}
	.xp-desktop {
		background-image: url('img/blis-2006.jpeg');
	}
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

</style>
