<script lang="ts">
    export let color: string = 'gray'
    export let hidden: boolean = false
</script>

<div class="button" class:hidden style="background-color: {color}" />

<style lang="scss">
    .button {
        display: inline-block;
        width: 2em;
        height: 1em;
        border: 1px solid gray;
        text-align: center;
        font-size: 2em;
        font-weight: bold;
        color: white;
        margin: 0.1em;

        // center vertically
        display: flex;
        align-items: center;
        justify-content: center;

        // transition
        transition: all 0.5s ease;
    }

    .hidden {
        height: 0;
        opacity: 0;
    }
</style>
