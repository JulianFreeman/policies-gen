<script>
    import { invoke } from "@tauri-apps/api/tauri";

    export let func;
    let name = "";
    let msg = "";

    async function greet() {
        msg = await invoke(func, { name });
    }
</script>

<div class="box m-4">
    <div class="columns">
        <div class="column">
            <input id="greet-input" placeholder="Enter a name ..." bind:value={name} class="input is-primary"/>
        </div>
        <div class="column">
            <button on:click={greet} class="button is-primary">Click</button>
        </div>
    </div>

    <p>{msg}</p>
</div>


