<script>
    import BrowserSwitch from "$lib/BrowserSwitch.svelte";
    import BrowserTab from "$lib/BrowserTab.svelte";

    import { SingleValues as chrome_settings } from "$lib/templates/chrome.json";
    import { SingleValues as edge_settings } from "$lib/templates/edge.json";
    import { SingleValues as brave_settings } from "$lib/templates/brave.json";

    const settings_dic = {
        "Chrome": chrome_settings,
        "Edge": edge_settings,
        "Brave": brave_settings,
    }

    let checked_browser = "Chrome";
    $: should_hidden = {
        "Chrome": checked_browser !== "Chrome",
        "Edge": checked_browser !== "Edge",
        "Brave": checked_browser !== "Brave",
    }
</script>


<div class="m-4">
    <div class="my-4">
        <BrowserSwitch bind:checked_browser />
    </div>
    <div>
        {#each Object.keys(settings_dic) as browser (browser + "Tab")}
            <BrowserTab browser={browser}
                        settings_info={settings_dic[browser]}
                        bind:hidden={should_hidden[browser]}
            />
        {/each}
    </div>

</div>

