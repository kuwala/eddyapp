<script lang="ts">
  import '7.css/dist/7.css'
  import Draggable from './Draggable.svelte';
  export let onClose: ()=>{};
  export let onMinimize: ()=>{};
  export let onMaximize: ()=>{};

 
	export let left = 600;
	export let top = 600;
  let minimized = false;
  function minimize() {
    minimized = true;
  }
  function maximize() {
    minimized = false;
  }
	

</script>

<!-- <div on:mousedown={onMouseMove} class="window glass draggable" style="left: {left}px; top: {top}px;"> -->
<Draggable {left} {top}>

<div class="window glass " >
  <div style="max-width: 320px">
    <div class="title-bar glass">
      <div class="title-bar-text">A glass window frame</div>
      <div class="title-bar-controls">
        {#if minimized === false}
        <button aria-label="Minimize" on:click={minimize}></button>
        {:else }
        <button aria-label="Maximize" on:click={maximize}></button>
        {/if}
        <button aria-label="Close" on:click={onClose}></button>
      </div>
    </div>
    <div class="window-body" class:minimized>
      <p>The background behind is blurred. Will it stretch to fit?</p>
      <!-- <iframe style="border: 0; width: 240px; height: 382px;" src="https://bandcamp.com/EmbeddedPlayer/album=3655657492/size=large/bgcol=ffffff/linkcol=0687f5/tracklist=false/transparent=true/" seamless><a href="https://eddyeddyeddy.bandcamp.com/album/swimming">Swimming by Eddy Eddy Eddy</a></iframe> -->
      <!-- <p>I guess a sound player is going to show up here eventually</p> -->
      <iframe title="audio player" style="border: 0; width: 100%; height: 42px;" src="https://bandcamp.com/EmbeddedPlayer/album=3655657492/size=small/bgcol=ffffff/linkcol=0687f5/artwork=none/transparent=true/" seamless><a href="https://eddyeddyeddy.bandcamp.com/album/swimming">Swimming by Eddy Eddy Eddy</a></iframe>
    </div>
  </div>
</div>
</Draggable>

<style>
  .minimized {
    display: none;
  }
</style>