<script>
    const browsers = [
        "Chrome",
        "Edge",
        "Brave",
    ];
    const icons = {
        "Chrome": "images/chrome_32.png",
        "Edge": "images/edge_32.png",
        "Brave": "images/brave_32.png",
    }
    export let checked_browser = "Chrome";
</script>

<div class="tabs is-toggle">
    <ul>
        {#each browsers as browser}
            <li class:is-active={checked_browser === browser}>
                <a href="/" on:click={() => checked_browser = browser}>
                    <img src={icons[browser]} alt={browser} class="image is-24x24" />
                    <span class="pl-1">{browser}</span>
                </a>
            </li>
        {/each}
    </ul>
</div>
