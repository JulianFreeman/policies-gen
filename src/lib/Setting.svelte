<script>
    import Switch from "$lib/Switch.svelte";
    export let setting_info;
    export let browser;
    let enabled = setting_info["enabled"];
    let allow_recommend = setting_info["allow_recommend"];
    let option = setting_info["default_value"];
</script>

<div class="box">
    <div class="columns mb-0">
        <div class="column">
            <h5 class="is-size-5 has-text-weight-bold">{setting_info["display_name"]}</h5>
        </div>
        <div class="column is-narrow">
            <Switch bind:checked={enabled} />
        </div>
    </div>

    {#each Object.keys(setting_info["values"]) as key (browser + setting_info["name"] + key)}
        <div class="py-1">
            <label class="radio">
                <input type="radio"
                       name={browser + setting_info["name"]}
                       checked={setting_info["default_value"] === key}
                       value={key}
                       bind:group={option}
                />
                {setting_info["values"][key]}
            </label>
        </div>
    {/each}

    {#if setting_info["allow_recommend"]}
        <div class="block is-flex is-justify-content-flex-end">
            <label class="checkbox">
                <input type="checkbox" bind:checked={allow_recommend} />
                设置为默认
            </label>
        </div>
    {/if}
</div>
