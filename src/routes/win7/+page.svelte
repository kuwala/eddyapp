<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>
<script type="ts">
	import "7.css/dist/7.css";

</script>

<div class="content">
	<h1>Not About this app</h1>

	<div class="window" style="margin: 32px; width: 250px">
		<div class="title-bar">
			<div class="title-bar-text">My First Program</div>
		</div>
		<div class="window-body">
			<p>Hello, world!</p>
		</div>
	</div>
	<div class="window" style="margin: 32px; width: 250px">
		<div class="title-bar">
			<div class="title-bar-text">My First Program</div>
			<div class="title-bar-controls">
				<button aria-label="Minimize"></button>
				<button aria-label="Maximize"></button>
				<button aria-label="Close"></button>
			</div>
		</div>
		<div class="window-body">
			<p>Hello, world!</p>
		</div>
	</div>

	<div class="win7">
		<button>Hey</button>
	</div>

	<p>
		This is a <a href="https://kit.svelte.dev">SvelteKit</a> app. You can make your own by typing the
		following into your command line and following the prompts:
	</p>

	<pre>npm create svelte@latest</pre>

	<p>
		The page you're looking at is purely static HTML, with no client-side interactivity needed.
		Because of that, we don't need to load any JavaScript. Try viewing the page's source, or opening
		the devtools network panel and reloading.
	</p>

	<p>
		The <a href="/todos">TODOs</a> page illustrates SvelteKit's data loading and form handling. Try using
		it with JavaScript disabled!
	</p>
</div>

<style>
	.content {
		width: 100%;
		max-width: var(--column-width);
		margin: var(--column-margin-top) auto 0 auto;
	}
</style>
