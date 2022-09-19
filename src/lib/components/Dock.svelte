<script lang="ts">
  /**
   * The Dock now emits a "clickEvent" message that can be used to get the xPosition of
   * where the mouse wasClicked. Used to select "which" icon was clicked on.
   */
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let element: HTMLElement | undefined = undefined;

  function dispatchClickPosition(event: MouseEvent) {
    let bounds = element?.getBoundingClientRect();
    if (bounds) {
      let xpos = Math.round(event.clientX - bounds.left);
      dispatch("clickEvent", {
        xPos: xpos,
      });
    }
  }
</script>

<div class="center-container">
  <img
    bind:this={element}
    on:click={dispatchClickPosition}
    class="dock"
    src="img/m1-dock.png"
    alt="macOS dock with lots of icons. including a trash can on the right."
  />
</div>

<style>
  .center-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
    /* fade in out */
    transition-duration: 3000ms;
    transition: opacity 0.9s ease-in-out;
    opacity: 0;
  }
  .center-container:hover {
    transition-duration: 3000ms;
    transition: opacity 0.5s ease-in-out;
    opacity: 1;
  }
  .dock {
    width: 80%;
  }
</style>
