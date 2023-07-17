<script lang="ts">
    import Letter from 'src/components/Letter.svelte'
    import { createEventDispatcher } from 'svelte'

    const dispatch = createEventDispatcher<{
        word: string
    }>()

    export let active: boolean = false
    export let letters: string[] = ['', '', '', '', '']

    $: if (letters.every((letter) => letter.length > 0)) {
        dispatch('word', letters.join(''))
    }

    let activeLetter = 0
</script>

<div class="row">
    <Letter bind:letter={letters[0]} active={activeLetter === 0} showButtons={active} on:letter={() => (activeLetter = 1)} on:focus />
    <Letter
        bind:letter={letters[1]}
        active={activeLetter === 1}
        showButtons={active}
        on:letter={() => (activeLetter = 2)}
        on:backspace={() => (activeLetter = 0)}
        on:focus
    />
    <Letter
        bind:letter={letters[2]}
        active={activeLetter === 2}
        showButtons={active}
        on:letter={() => (activeLetter = 3)}
        on:backspace={() => (activeLetter = 1)}
        on:focus
    />
    <Letter
        bind:letter={letters[3]}
        active={activeLetter === 3}
        showButtons={active}
        on:letter={() => (activeLetter = 4)}
        on:backspace={() => (activeLetter = 2)}
        on:focus
    />
    <Letter bind:letter={letters[4]} active={activeLetter === 4} showButtons={active} on:backspace={() => (activeLetter = 3)} on:focus />
</div>

<style lang="scss">
    .row {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }
</style>
