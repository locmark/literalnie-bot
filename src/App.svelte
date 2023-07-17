<script lang="ts">
    import Row from 'src/components/Row.svelte'

    let name: string = 'world'

    let activeRow = 0

    let words: string[] = []

    function onWord(index: number) {
        return (event: CustomEvent<string>) => {
            console.log(index)
            words[index] = event.detail
        }
    }
</script>

<main>
    <Row active={activeRow === 0} on:focus={() => (activeRow = 0)} on:word={onWord(0)} />
    <Row active={activeRow === 1} on:focus={() => (activeRow = 1)} on:word={onWord(1)} />
    <Row active={activeRow === 2} on:focus={() => (activeRow = 2)} on:word={onWord(2)} />
    <Row active={activeRow === 3} on:focus={() => (activeRow = 3)} on:word={onWord(3)} />
    <Row active={activeRow === 4} on:focus={() => (activeRow = 4)} on:word={onWord(4)} />
    <Row active={activeRow === 5} on:focus={() => (activeRow = 5)} on:word={onWord(5)} />
</main>

<style lang="scss">
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;

        h1 {
            color: #ff3e00;
            text-transform: uppercase;
            font-size: 4em;
            font-weight: 100;
        }

        @media (min-width: 640px) {
            max-width: none;
        }
    }
</style>
