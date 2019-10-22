<script>
	export let segment;
</script>

<style>
	nav {
		height: 3rem;
		display: flex;
		justify-content: center;
		align-items: center;
		border-bottom: 1px solid black;
		background-color: var(--background-color);
		/* Not rendering for some reason
		box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
		box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23); */
	}



	.selected {
		position: relative;
		display: inline-block;
	}

	.selected::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: rgb(255,62,0);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 1em 0.5em;
		display: block;
	}
</style>

<nav>
   
	<ul class="">
	    <li> EphemeraSearch </li>
		<!-- 
		<li><a class='{segment === undefined ? "selected" : ""}' href='.'>home</a></li>
		<li><a class='{segment === "about" ? "selected" : ""}' href='about'>about</a></li>
		-->
	</ul>
</nav>