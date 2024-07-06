<script>
    export let checked;
</script>

<div class="switch-container">
    <label class="switch">
        <input type="checkbox" class="switch-checkbox" bind:checked />
        <span class="slider"></span>
    </label>
</div>

<style>
    /* The switch - the box around the slider */
    .switch-container {
        width: 51px;
        height: 31px;
        position: relative;
    }

    /* Hide default HTML checkbox */
    .switch-checkbox {
        opacity: 0;
        width: 0;
        height: 0;
        position: absolute;
    }

    .switch {
        width: 100%;
        height: 100%;
        display: block;
        background-color: #e9e9eb;
        border-radius: 16px;
        cursor: pointer;
        transition: all 0.2s ease-out;
    }

    /* The slider */
    .slider {
        width: 27px;
        height: 27px;
        position: absolute;
        left: calc(50% - 27px / 2 - 10px);
        top: calc(50% - 27px / 2);
        border-radius: 50%;
        background: #FFFFFF;
        box-shadow: 0 3px 8px rgba(0, 0, 0, 0.15), 0 3px 1px rgba(0, 0, 0, 0.06);
        transition: all 0.2s ease-out;
        cursor: pointer;
    }

    .switch:has( > .switch-checkbox:checked) {
        background-color: #4258ff;
    }

    .switch:has( > .switch-checkbox:checked) .slider {
        left: calc(50% - 27px / 2 + 10px);
        top: calc(50% - 27px / 2);
    }

</style>
