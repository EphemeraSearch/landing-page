<script>
import Picture from './Picture.svelte';
let isHighlighted = 2;
let timeout;



function changeHighlight(el) {
  clearTimeout(timeout);
  isHighlighted = el;
  timeout = setTimeout(() => {
              isHighlighted = 2
            }, 3000);
}

</script> 
 
 


<style>
.parent {
    width: 100%;
    font-size:1rem;
    max-width: 35rem;
    position: relative;
    z-index: 1;
    margin-top: 3rem;
}

img, .wrapper {
    width: calc(5rem + 10vw);
    animation-name: shrink;
    animation-duration: 150ms;
    margin-right: 1rem;
    
}


.date {
    width: 4rem;
    text-align: center;
}

.parent > * {
  opacity: 0.5;
  z-index: 2;
  position: relative;
  transition:  opacity 100ms 150ms, z-index 0s 150ms, box-shadow 120ms 0ms;
}

.parent > .highlight {
  opacity: 1;
  font-size: var(--s3);
  position: relative;
  z-index: 3;
  transition: z-index 0s 150ms, opacity 350ms 150ms, box-shadow 350ms 150ms ;
}


.parent .highlight img,
.parent .highlight .wrapper {
    animation-name: grow;
    animation-duration: 350ms;
    animation-delay: 150ms;
    animation-fill-mode: both;
}


@keyframes grow {
  0%   {transform: scale(1)}
  100% {transform: scale(1.5);}
}

@keyframes shrink {
  from   {transform: scale(1.5)}
  to {transform: scale(1);}
}
</style>
    


<div class="flex flex-col items-center stack-small">
	<h2 class="text-center"> Scroll Through the Past</h2>
	<p class="sm:text-center">Peer into history visually. See old photography, artwork, and humour.</p>
	
    
    <ul class="parent">
      <li class="flex items-center justify-between {isHighlighted === 1 ? 'highlight' : ''}"
          on:click={() => changeHighlight(1)}>
        <p class="font-bold date">1940</p>
        <div class="wrapper">
          <Picture host="groundedsage" imgName="landscape" imgAlt="An old black and white landscape photo"/>
        </div>
          
        
      <!--<img src="landscape-photo.jpg" alt="Old Postcard" >-->
      </li>
      <li class="flex items-center justify-between {isHighlighted === 2 ? 'highlight' : ''}"
           on:click={() => changeHighlight(2)}>
        <p  class="font-bold date">1950</p>
        <div class="wrapper">
          <Picture host="groundedsage" imgName="thanksgiving" imgAlt="Thanksgiving art on a postcard"/>
        </div>
        <!-- <img src="thanksgiving.jpg" alt="Old Postcard" >-->
      </li>
      <li class="flex items-center justify-between {isHighlighted === 3 ? 'highlight' : ''}"
           on:click={() => changeHighlight(3)}>
        <p  class="font-bold date">1960</p>
        <div class="wrapper">
          <Picture host="groundedsage" imgName="motorcycle" imgAlt="Black and white photo of an old motorcycle"/>
        </div>
        <!-- <img src="motorcycle.jpg" alt="Old Postcard"> -->
      </li>
	</ul>

</div>