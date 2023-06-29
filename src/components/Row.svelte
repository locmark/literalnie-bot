<script lang="ts">
    import Letter from 'src/components/Letter.svelte'
</script>

<div class="row">
    <Letter letter="A" />
    <Letter letter="B" />
    <Letter letter="C" />
    <Letter letter="D" />
    <Letter letter="E" />
</div>

<style lang="scss">
    .row {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }
</style>
