<script lang="ts">
    import { LetterScore } from 'src/types.js'
    import ScoreButton from 'src/components/ScoreButton.svelte'

    export let letter: string = ''
    export let score: LetterScore = LetterScore.GRAY
</script>

<div class="container">
    <ScoreButton color="#538d4e" />
    <div class="input">
        {letter}
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
</style>
