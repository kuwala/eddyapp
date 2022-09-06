<script lang="ts">
  import '7.css/dist/7.css'
  import Draggable from './Draggable.svelte';
  export let onClose;
 
	export let left = 600;
	export let top = 600;
	
	// let moving = false;
	
	// function onMouseDown() {
	// 	moving = true;
  //   console.log("Hey");
	// }
	
	// function onMouseMove(e) {
	// 	if (moving) {
	// 		left += e.movementX;
	// 		top += e.movementY;
	// 	}
	// }
	
	// function onMouseUp() {
	// 	moving = false;
	// }
	
	// $: console.log(moving);
</script>

<style>
</style>
<!-- <div on:mousedown={onMouseMove} class="window glass draggable" style="left: {left}px; top: {top}px;"> -->
<Draggable {left} {top}>

<div class="window glass " >
  <div style="max-width: 320px">
    <div class="title-bar glass">
      <div class="title-bar-text">A glass window frame</div>
      <div class="title-bar-controls">
        <button aria-label="Minimize"></button>
        <button aria-label="Close" on:click={onClose()}></button>
      </div>
    </div>
    <div class="window-body">
      <p>The background behind is blurred. Will it stretch to fit?</p>
      <!-- <p>I guess a sound player is going to show up here eventually</p> -->
    </div>
  </div>
</div>
</Draggable>