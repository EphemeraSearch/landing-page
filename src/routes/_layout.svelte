<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		box-sizing: border-box;
	}

	h1 { 
		position: absolute;
		z-index: 5;
		color: white;
		font-weight: 900;
		font-size: 3em;
		padding: 1.5rem;
		line-height: 1.2em;
	}

	.container-svelte {
		position: relative;
		width: 100%;
		max-height: 50vh;
		overflow: hidden;
		display: flex;
	}

	img { 
		width: 100%;
		object-fit: cover;
		filter: blur(1px);
	}

	.img-gradient{
		content: "";
		background-image: linear-gradient(to top, black, rgba(0,0,0,0.4));
		position: absolute;
		top: 0;
		width: 100%;
		height: 100%;
	}
	.container h1 {
		align-self: center;
		letter-spacing: 0.02em;
	}

@media (max-width: 600px) {
	.sm\:heading {
		font-size:  calc(var(--s2) + 0.5vw);
	}
}


@media (min-width: 600px) {
	img { 
		filter: blur(3px);
	}
}


</style>

<Nav {segment}/>

<header>
<div class="bg-img"></div>
</header>


<div class="container-svelte">
  <img src="banner-postcard.jpg" alt="Old Postcard">
  <div class="img-gradient"></div>
  <h1 class="sm:heading">Explore the connections and history of the worlds postcards</h1>
</div>



<main class="stack-xl mt-12 px-6">
	<slot></slot>
</main>