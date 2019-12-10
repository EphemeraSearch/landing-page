<script>
    export let segment;
</script>

<style>
    nav {
        height: 3rem;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: var(--background-color);
        box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
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
        <li class="flex font-extrabold items-center">
        <svg class="mr-4 w-8" fill="none" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 465 321"><rect x="6.5" y="6.5" width="452" height="308" rx="13.5" stroke="#000" stroke-width="13"/><rect x="349.642" y="41.362" width="74.567" height="75.227" rx="7" transform="rotate(-.58 349.642 41.362)" fill="#4DFFFF" stroke="#000" stroke-width="6"/><path stroke="#000" stroke-width="6" d="M280 54v218"/><path stroke="#000" stroke-width="7" d="M45 60.5h199M45 86.5h180M45 182.5h136M45 148.5h180M45 116.5h199"/></svg>
         EphemeraSearch </li>
        <!--
        <li><a class='{segment === undefined ? "selected" : ""}' href='.'>home</a></li>
        <li><a class='{segment === "about" ? "selected" : ""}' href='about'>about</a></li>
        -->
    </ul>
</nav>
