<script>
    let count = 0;
    $: doubled = count * 2;
    function increaseCount() {
        count += 1;
    }
</script>

<button on:click={increaseCount}>
    Button clicked
    {count}
    doubled
    {doubled}
    {count === 1 ? 'time' : 'times'}
</button>
