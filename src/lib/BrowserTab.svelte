<script>
    import Setting from "$lib/Setting.svelte";
    export let browser;
    export let settings_info;
    export let hidden;
</script>

<div class:is-hidden={hidden}>
    {#each settings_info as setting (browser + "=" + setting["name"])}
        <Setting setting_info={setting} {browser} />
    {/each}
</div>
