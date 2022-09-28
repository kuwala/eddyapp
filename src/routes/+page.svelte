<script lang="ts">
	import Draggable from '$lib/components/Draggable.svelte';
	import MiniWindow from '$lib/components/MiniWindow.svelte';
	import Dock from '$lib/components/Dock.svelte'
	import AudioPlayerWindow from '$lib/components/AudioPlayerWindow.svelte';
	import Counter from '$lib/Counter.svelte';
	import '7.css/dist/7.css';
    import GalleryWindow from '$lib/components/GalleryWindow.svelte';

	let showAudioPlayer= true;
	let showGallery = true;

	function selectIcon(event:CustomEvent) {
		let mouseX = event.detail.xPos;
		console.log(mouseX);

		if (mouseX >= 0 && mouseX <= 45) {
		showAudioPlayer = true;
		} else if (mouseX >= 45 && mouseX <= 85) {
			showGallery = true;
		} else if (mouseX >= 85 && mouseX <= 125) {
			showGallery = false;
		}

	}

	
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Eddy Eddy Eddy's group page" />
</svelte:head>

<section >
	<span class="slow-fadeout fade-in">
		<p> Eddy Eddy Eddy</p>
		<p> Eddy Eddy Eddy</p>
		<p> Eddy Eddy Eddy</p>
	</span>
	<div class="xp-desktop">

			<br/> <br/> <br/> <br/> <br/> <br/> <br/> <br/> <br/>

			<AudioPlayerWindow bind:showWindow={showAudioPlayer} ></AudioPlayerWindow>
			<GalleryWindow bind:showWindow={showGallery}></GalleryWindow>
			<h1>Uh hello</h1>

			


	</div> <!-- end desktop-->
	  <div style="margin-top: 58px;">
			<Dock on:clickEvent={selectIcon}/>

		</div>

</section>

<style>
	h1 {
		width: 100%;
		transition: opacity 3s ease-in-out;
		opacity: 0;
		z-index: 3;
		position: relative;
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
		overflow: hidden;
		position: relative;
	}
	.xp-desktop:hover {
		box-shadow: 0 0 8px 4px rgba(0, 140, 186, 0.5);
		transition: box-shadow 0.5s ease-in-out;
	}
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}
	.slow-fadeout{
		animation-name: fadeOutAnim;
		animation-duration: 6s;
		animation-iteration-count: 1;
		animation-fill-mode: forwards;
		/* lets the affected element keep its final animation value (stay invisble)*/
	}



	@keyframes fadeOutAnim {
		from {
			opacity: 1;
		}

		to {
			opacity: 0;
		}
	}



</style>
