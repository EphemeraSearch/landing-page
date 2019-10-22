<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
	main {
		position: relative;
		max-width: 56rem;
	}

</style>

<Nav {segment}/>

<svg class="fixed w-screen h-screen -mt-12" style="z-index: -1; background-color: hsl(42, 33%, 84%)" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
  <defs>
    <filter id="filter_texture">
      <feTurbulence type="fractalNoise" baseFrequency="0.007" stitchTiles="stitch" numOctaves="5" result="noise"></feTurbulence>
      <feDiffuseLighting in="noise" lighting-color="hsl(42, 72%, 94%)" surfaceScale="5">
        <feDistantLight id="distLight" azimuth="35" elevation="60"></feDistantLight>
      </feDiffuseLighting>
    </filter>
  </defs>
  <rect opacity=".8" filter="url(#filter_texture)" width="100%" height="100%"></rect>
</svg>
<main class="stack-xl px-6 mx-auto">
	<slot></slot>
</main>