<script>
    let { start, end } = $state("");
    let { date_range = $bindable() } = $props()

    $effect(() => {
        date_range = [start, end]
    })
</script>

<input type="date" bind:value={start}>
<input type="date" bind:value={end}>