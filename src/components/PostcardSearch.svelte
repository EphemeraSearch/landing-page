<script>
import { fade } from 'svelte/transition';
import { onMount } from 'svelte';
import SearchIcon from './SearchIcon.svelte';
import Picture from './Picture.svelte';

let visible = false;
let js = false;
let padright = "";


function typewriter(node, { 
    speed = 400,
    delay = 0
    }) {

	const valid = (
		node.childNodes.length === 1 &&
		node.childNodes[0].nodeType === 3
	);

	

	if (!valid) {
		throw new Error(`This transition only works on elements with a single text node child`);
	}


	const text = node.textContent;
	const duration = text.length * speed;

	return {
        delay,
		duration,
		tick: t => {
			const i = ~~(text.length * t);
            node.textContent = text.slice(0, i);
        },
	};
}

function delay(t,b) {
    setTimeout(function() {visible = b}, t)
}





onMount(async () => {
    visible = true;
    js = true;
    
});

</script>



<style>

.search__bar {
	border-radius: 2rem;
	width: 90vw;
    max-width: 60ch;
    background-color: var(--background-color);
    box-shadow: inset 0 1px 3px rgba(0,0,0,0.12), inset 0 1px 2px rgba(0,0,0,0.24);

 }

/*
 .search__details img {
	 width: calc(300px + 25vw);
	 height: auto;
     margin-left: calc(-2rem - 150px);
	 box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
 }

 */

 .wrapper {
     width: calc(200px + 25vw);
     margin-left: calc(-2rem - 150px);
     
 }


.typewriter-cursor {
    border-right-width: 2px;
    border-right-style: solid;
    border-right-color: darkslategrey;
    box-sizing: border-box;
}

 .blinking {
 	animation:  blink 0.75s step-end infinite;
    border-right-color: rgb(27, 23, 23) !important;
}

@keyframes blink {
    from, to { 
        border-color: transparent 
    }
    50% { 
        border-color: grey; 
    }
}

.hidden-text {
    color: rgba(0,0,0,0);
}

.border-b {
    border-bottom: 1px solid black;
}


</style>

<div class="flex flex-col items-center stack-small">

<h2 class="text-center"> Details You Can Search</h2>


	<div class="search__bar p-4 border border-solid border-gray-600 flex h-12 items-center">
	<SearchIcon/>

	{#if visible}
	<p  class="ml-4 tracking-wider typewriter-cursor" 
        in:typewriter 
        on:introend="{(n) => {delay(3000, false); n.target.classList.add('blinking')}}" 
        out:fade
        on:outroend="{() => delay(2000, true)}">

        Franklin
    </p>
    {:else if js}
    <p class="typewriter-cursor blinking h-5 w-4"
        in:fade="{{delay: 400}}"></p>
    {:else}
    <p class="ml-4 tracking-wider" >Franklin</p>
	{/if}

    </div>


	<div class="search__details flex items-center">
    <div class="wrapper mr-6">
    <Picture host="groundedsage" imgName="main-postcard" imgAlt="A postcard with handwritten details" />
    </div>
		<!-- <img src="main-postcard.jpg" alt="Old Postcard" class="mr-6">-->
		<ul class="stack-small">
			<li class="flex">
				<span class="w-20">Sender:</span>
                    <div class="relative">

                            {#if visible}
                            <span   class="font-light absolute hidden-text tracking-wider pl-1" 
                                    style="background: yellow;" 
                                    in:typewriter
                                    on:introstart="{(n) => n.target.classList.remove('pr-1')}"
                                    on:introend="{(n) => n.target.classList.add('pr-1')}"
                                    out:fade
                                    >
                                Franklin
                            </span>
                            <span   class="font-light absolute tracking-wider px-1 border-b w-20"
                                    out:fade="{{duration: 0}}">Franklin</span>
                            {:else if js}
                            <span class="font-light absolute tracking-wider px-1 border-b w-20">Franklin</span>
                            {:else}
                            <span class="font-light px-1 border-b w-20" style="background: yellow;">Franklin</span>
                            {/if}
                    </div>

	
			</li>
			<li class="flex">
				<span class="w-20">Recipient:</span>
				<span class="font-light px-1 border-b w-20">Phillip</span>
			</li>
			<li class="flex">
				<span class="w-20">Year:</span>
				<span class="font-light px-1 border-b w-20">1899</span>
			</li>
		</ul>
	</div>
</div>