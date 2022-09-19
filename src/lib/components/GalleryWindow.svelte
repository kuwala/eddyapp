<script lang="ts">
	import MiniWindow from "$lib/components/MiniWindow.svelte";
	export let showWindow = true;

	let images = [
		{
		fileSrc: "/img/powell-butte-chill-2021.png",
		altText: "eddy eddy eddy sitting around chilling at powell butte."
		},
		{
		fileSrc: "/img/bliss-2017.jpeg",
		altText: "Bliss 2017."
		},
		{
		fileSrc: "/img/bliss-2006.jpeg",
		altText: "bliss 2006."
		},
	]

let imageIndex = 0;
function increment() {
	imageIndex++;
	if(imageIndex >= images.length) {
		imageIndex = 0;
	}
}
function decrement() {
	imageIndex --;
	if(imageIndex<0) {
		imageIndex = images.length - 1;
	}
}

</script>

{#if showWindow}
	<MiniWindow
		maxWidth={340}
		onClose={() => (showWindow = false)}
		left={600}
		top={600}
	>
		<span slot="title"> Photos </span>
		<span slot="body">
			<div class="thumbnail">
				<img
					src="{images[imageIndex].fileSrc}"
					alt="{images[imageIndex].altText}"
				/>
			</div>
			<button on:click={decrement}>Prev</button>
			<button>-.</button>
			<button>.-</button>
			<button on:click={increment}>Next</button>
		</span>
	</MiniWindow>
{/if}

<style>
	img {
		max-width: 312px;
		border-radius: 3px;
		transition: box-shadow 0.5s ease-in-out;
		/* heigh: auto; */
	}
	img:hover {
		transition: box-shadow 0.5s ease-in-out;
		box-shadow: 0 0 8px 4px rgba(0, 140, 186, 0.5);
	}
</style>
