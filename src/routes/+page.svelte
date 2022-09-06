<script lang="ts">
	import Draggable from '$lib/components/Draggable.svelte';
	import MiniWindow from '$lib/components/MiniWindow.svelte';
	import Dock from '$lib/components/Dock.svelte'
	import Counter from '$lib/Counter.svelte';
	import '7.css/dist/7.css';

	let showWindow = true;
	
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Eddy Eddy Eddy's group page" />
</svelte:head>

<section >
	<p> Eddy Eddy Eddy</p>
	<p> Eddy Eddy Eddy</p>
	<p> Eddy Eddy Eddy</p>
	<div class="xp-desktop">

		<div class="centered-divd">
			<br/> <br/> <br/> <br/> <br/> <br/> <br/> <br/> <br/>
			<div class="centered-div">

			{#if showWindow}
				<MiniWindow onClose={() => showWindow = false} />
			{/if}
			<h1>Uh hello</h1>
			</div>

			

		</div>

	</div> <!-- end desktop-->
	<br/><br/><br/>
<br/>
			<Dock on:click={()=> {showWindow = true}}/>


	

</section>

<style>
	h1 {
		width: 100%;
		transition: opacity 3s ease-in-out;
		opacity: 0;
	}
	.fade-in {

		transition: opacity 3s ease-in-out;
		opacity: 1;
	}
	h1:hover {
		transition: opacity .3s ease-in-out;
		opacity: 1;
	}
	.centered-div {
		margin: 0 auto;
	}
	.xp-desktop {
		width: 900px;
		height: 675px;
		background: url('img/bliss-2006.jpeg') no-repeat center center ; /* fixed */
		-webkit-background-size: cover;
		-moz-background-size: cover;
		-o-background-size: cover;
		background-size: cover;

		transition: box-shadow 0.5s ease-in-out;
	}
	.xp-desktop:hover {
		box-shadow: 0 0 8px 4px rgba(0, 140, 186, 0.5);
		transition: box-shadow 0.5s ease-in-out;
	}
	.center-container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}


</style>
