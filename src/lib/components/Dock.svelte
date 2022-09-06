<script lang="ts">

</script>

<div class="center-container" on:click>
  <img class="dock" src="img/m1-dock.png" alt="macOS dock with lots of icons. including a trash can on the right.">
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