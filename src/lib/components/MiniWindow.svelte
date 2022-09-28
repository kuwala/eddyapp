<script lang="ts">
  import '7.css/dist/7.css'
  import Draggable from './Draggable.svelte';
    import MenuBar from './MenuBar.svelte';
  export let onClose: ()=>{};
  let onMinimize: ()=>{};
  let onMaximize: ()=>{};
  export let maxWidth = 320;
  export let zIndex = 1;
  export let menuBar = true;

 
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
<Draggable {left} {top} {zIndex}>

<div class="window glass " style="z-index:{zIndex}" >
  <div style="max-width: {maxWidth}px">
    <div class="title-bar glass">
      <div class="title-bar-text">
        <slot name="title"></slot></div>
      <div class="title-bar-controls">
        {#if minimized === false}
        <button aria-label="Minimize" on:click={minimize}></button>
        {:else }
        <button aria-label="Maximize" on:click={maximize}></button>
        {/if}
        <button aria-label="Close" on:click={onClose}></button>
      </div>
    </div>
    {#if menuBar === true}
      <MenuBar></MenuBar>
    {/if}
    
    <div class="window-body" class:minimized>
      <slot name="body">

      </slot>
    </div>
  </div>
</div>
</Draggable>
<style>
  .minimized {
    display: none;
  }
</style>