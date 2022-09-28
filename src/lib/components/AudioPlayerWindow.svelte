<script lang="ts">
  import MiniWindow from "$lib/components/MiniWindow.svelte";
	export let showWindow = true;

</script>
{#if showWindow}
	<MiniWindow onClose={() => showWindow = false} left={41} top={53} zIndex={4}>
		<span slot="title">
		A new release
		</span>
		<span slot="body">
      <!-- <iframe style="border: 0; width: 240px; height: 382px;" src="https://bandcamp.com/EmbeddedPlayer/album=3655657492/size=large/bgcol=ffffff/linkcol=0687f5/tracklist=false/transparent=true/" seamless><a href="https://eddyeddyeddy.bandcamp.com/album/swimming">Swimming by Eddy Eddy Eddy</a></iframe> -->
      <!-- <p>I guess a sound player is going to show up here eventually</p> -->
      <iframe title="audio player" style="border: 0; width: 100%; height: 42px;" src="https://bandcamp.com/EmbeddedPlayer/album=3655657492/size=small/bgcol=ffffff/linkcol=0687f5/artwork=none/transparent=true/" seamless><a href="https://eddyeddyeddy.bandcamp.com/album/swimming">Swimming by Eddy Eddy Eddy</a></iframe>
		</span>

	</MiniWindow>
{/if}

<style>
</style>

