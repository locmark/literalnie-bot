<script lang="ts">
    import Letter from 'src/components/Letter.svelte'

    export let letters: string[] = ['', '', '', '', '']
</script>

<div class="row">
    <Letter letter={letters[0]} />
    <Letter letter={letters[1]} />
    <Letter letter={letters[2]} />
    <Letter letter={letters[3]} />
    <Letter letter={letters[4]} />
</div>

<style lang="scss">
    .row {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }
</style>
