<script lang="ts">
	export let left = 600;
	export let top = 700;
	export let zIndex = 1;
	
	let moving = false;
	
	function onMouseDown() {
		moving = true;
	}
	
	function onMouseMove(e:MouseEvent) {
		if (moving) {
			left += e.movementX;
			top += e.movementY;
		}
	}
	
	function onMouseUp() {
		moving = false;
	}
	
// 	$: console.log(moving);
</script>

<style>
	.draggable {
		user-select: none;
		cursor: move;
		position: absolute;
	}
</style>

<div on:mousedown={onMouseDown} style="left: {left}px; top: {top}px; z-index: {zIndex}" class="draggable">
	<slot></slot>
</div>

<svelte:window on:mouseup={onMouseUp} on:mousemove={onMouseMove} />