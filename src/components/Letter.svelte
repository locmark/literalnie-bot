<script lang="ts">
    import ScoreButton from 'src/components/ScoreButton.svelte'
    import { LetterScore } from 'src/types.js'
    import { createEventDispatcher } from 'svelte'

    const dispatch = createEventDispatcher<{
        click: void
        backspace: void
    }>()

    export let letter: string = ''
    export let score: LetterScore = LetterScore.GRAY

    function onInput(event: Event & { currentTarget: EventTarget & HTMLInputElement }) {
        letter = (event.target as HTMLInputElement).value.toUpperCase()
        // limit to one character
        if (letter.length > 1) {
            letter = letter[letter.length - 1]
        }

        // only allow letters
        if (!letter.match(/[a-z ęóąśłżźćń]/i)) {
            letter = ''
        }

        if (letter.length > 0) {
            dispatch('click')
        } else {
            dispatch('backspace')
        }
    }
</script>

<div class="container">
    <ScoreButton color="#538d4e" />
    <div class="input">
        <input type="text" on:input={onInput} value={letter} />
    </div>
    <ScoreButton color="#b59f3b" />
</div>

<style lang="scss">
    .input {
        display: inline-block;
        width: 2em;
        height: 2em;
        border: 1px solid gray;
        text-align: center;
        font-size: 2em;
        font-weight: bold;
        color: white;
        background-color: #787c7e;
        margin: 0.1em;

        // center vertically
        display: flex;
        align-items: center;
        justify-content: center;
    }

    input {
        width: 100%;
        height: 100%;
        border: none;
        background-color: transparent;
        text-align: center;
        font-size: 1.5em;
        font-weight: bold;
        color: white;
    }
</style>
