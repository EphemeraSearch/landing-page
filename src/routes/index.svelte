<script>
import PostcardSearch from '../components/PostcardSearch.svelte';
import Timeline from '../components/TimelineCarousal.svelte';
import Picture from '../components/Picture.svelte';

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

	header img,
	.wrapper { 
		width: 100%;
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
		box-shadow: inset 0 10px 20px rgba(0,0,0,0.19),inset 0 6px 6px rgba(0,0,0,0.23);
	}

@media (max-width: 600px) {
	.sm\:heading {
		font-size:  calc(var(--s2) + 0.5vw);
	}
}


@media (min-width: 600px) {
	header img,
	.wrapper { 
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
	<div class="wrapper">
	<picture>
    <source type="image/webp" 
        srcset="https://res.cloudinary.com/groundedsage/image/upload/w_200,c_fit/f_webp/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 200w, 
                https://res.cloudinary.com/groundedsage/image/upload/w_400,c_fit/f_webp/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 400w,
                https://res.cloudinary.com/groundedsage/image/upload/w_800,c_fit/f_webp/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 800w,
                https://res.cloudinary.com/groundedsage/image/upload/w_1200,c_fit/f_webp/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 1200w, 
            https://res.cloudinary.com/groundedsage/image/upload/w_1600,c_fit/f_webp/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 1600w,
            https://res.cloudinary.com/groundedsage/image/upload/w_2400,c_fit/f_webp/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 2400w"		 

        sizes="800px">
    <source type="image/jpg"  
        srcset="https://res.cloudinary.com/groundedsage/image/upload/w_200,c_fit/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 200w, 
                https://res.cloudinary.com/groundedsage/image/upload/w_400,c_fit/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 400w,
                https://res.cloudinary.com/groundedsage/image/upload/w_800,c_fit/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 800w,
                https://res.cloudinary.com/groundedsage/image/upload/w_1200,c_fit/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 1200w, 
            https://res.cloudinary.com/groundedsage/image/upload/w_1600,c_fit/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 1600w,
            https://res.cloudinary.com/groundedsage/image/upload/w_2400,c_fit/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg 2400w
            " 
        sizes="800px">
        <img    src="https://res.cloudinary.com/groundedsage/image/upload/w_400,c_fit/f_webp/q_auto/v1571763923/ephemerasearch/banner-postcard.jpg" 
                alt="Presentational image" 
                sizes="auto" 
                class="w-full"
                >
</picture>
	</div>
	<!-- <img src="banner-postcard.jpg" alt="Old Postcard"> -->
	<div class="img-gradient"></div>
	<h1 class="sm:heading">Explore the connections and history of the worlds postcards</h1>
</header>




<PostcardSearch/>
<Timeline/>

<section class="flex flex-col items-center stack-small">
<h2 class="text-center"> Track cards across the globe</h2>
<p class="sm:text-center">Follow postcards sent to a specific address and discover interesting relationships. Across time and space.</p>
 <div class="w-56 h-56 rounded-full overflow-hidden relative">
 <Picture host="groundedsage" imgName="map" alt="World map with pins and string between the pins connecting places" c="object-cover w-56 h-56"/>
 <!--<img  src="map.jpg" alt="" class="object-cover w-56 h-56"> -->
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

<section class="w-60ch mx-auto">
	<h2 class="text-center">Sign up for our early Beta</h2>
	<form class="stack-small flex flex-col" name="contact" method="post" netlify="true" netlify-honeypot="bot-field">
		<input type="hidden" name="form-name" value="contact">
		<label for="name" >
			<div class="flex justify-between">Name: <span class="text-red-800">* required</span></div>
			<input class="pl-4 py-2 w-full" type="text" name="name" placeholder="Susan Smith">
		</label>
		
	
		<label for="email" >
			<div class="flex justify-between">Email: <span class="text-red-800">* required</span></div>
			<input class="pl-4 py-2 w-full" type="email" name="email" placeholder="susan@historian.com">
		</label>
		

		<button class="border-none w-1/2 h-12  hover:underline cursor-pointer hover:bg-gray-900 self-center bg-black text-white" type="submit">Sign me up!</button>
	</form>
</section>