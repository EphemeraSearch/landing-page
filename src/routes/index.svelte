<script>

import PostcardSearch from '../components/PostcardSearch.svelte'
import Timeline from '../components/TimelineCarousal.svelte'


</script>

<style>
	h1 { 
		position: absolute;
		z-index: 5;
		color: white;
		font-weight: 900;
		font-size: 3em;
		padding: 1.5rem;
		line-height: 1.2em;
	}


	header {
		width: calc(100% + 3rem);
		position: relative;
		max-height: 50vh;
		overflow: hidden;
		display: flex;
	}

	header img { 
		width: 100%;
		object-fit: cover;
		filter: blur(1px);
	}

	header .img-gradient{
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

	.inside-shadow {
		box-shadow: inset 0 0 10px #000000
	}

@media (max-width: 600px) {
	.sm\:heading {
		font-size:  calc(var(--s2) + 0.5vw);
	}
}


@media (min-width: 600px) {
	header img { 
		filter: blur(3px);
	}
}

@media (min-width: 78rem) {
	header {
		border-bottom-right-radius: 1rem;
		border-bottom-left-radius: 1rem;
	}
}
</style>


<svelte:head>
	<title>EphemeraSearch</title>
</svelte:head>


<header class="container-svelte -mx-6">
  <img src="banner-postcard.jpg" alt="Old Postcard">
  <div class="img-gradient"></div>
  <h1 class="sm:heading">Explore the connections and history of the worlds postcards</h1>
</header>




<PostcardSearch/>
<Timeline/>

<section class="flex flex-col items-center stack-small">
<h2> Track cards across the globe</h2>
<p class="text-center">Follow postcards sent to a specific address and discover interesting relationships. Across time and space.</p>
 <div class="w-56 h-56 rounded-full overflow-hidden relative">
 <img  src="map.jpg" alt="" class="object-cover w-56 h-56">
 <div class="w-full h-full absolute top-0 w-56 h-56 rounded-full inside-shadow"></div>
 </div>
</section>

<section class="stack-small flex flex-col items-center">
	<h2> Contribute to the Discovery</h2>
	<div class="mx-auto stack-small">
	<section >
			<h3>Unbox Your Collection</h3>
			<p>Share your collection and see what unique discoveries you find.</p>
	</section>

	<section>
			<h3>Help with the Hard Stuff</h3>
			<p>When it comes to decyphering old and faded handwriting. Humans are way better than machines. Every bit of help makes more discoveries possible.</p>
	</section>
	</div>
</section>