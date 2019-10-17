<script>

import PostcardSearch from '../components/PostcardSearch.svelte'
import Timeline from '../components/TimelineCarousal.svelte'


</script>



<svelte:head>
	<title>EphemeraSearch</title>
</svelte:head>





<PostcardSearch/>

<Timeline/>
	
	


<section class="flex flex-col items-center stack-small">
<h2> Track cards across the globe</h2>
<p>Follow postcards sent to a specific address and discover interesting relationships. Across time and space.</p>
<img  src="map.jpg" alt="" class="object-cover w-56 h-56 rounded-full">
</section>

<section class="stack-small flex flex-col items-center">
	<h2> Contribute to the Discovery</h2>
	<section class="flex">
		<img src="box-holding.png" alt="Old Postcard" class="h-48">
		<div class="p-6">
			<h3>Unbox Your Collection</h3>
			<p>Share your collection and see what unique discoveries you find.</p>
		</div>
	</section>

	<section class="flex flex-row-reverse">
		<img src="keyboard.jpg" alt="Typing on the computer keyboard" class="h-48">
		<div class="p-6">
			<h3>Help with the Hard Stuff</h3>
			<p>When it comes to decyphering old and faded handwriting. Humans are way better than machines. Every bit of help makes more discoveries possible.</p>
		</div>
	</section>
</section>