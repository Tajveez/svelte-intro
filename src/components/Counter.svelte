<script>
    let count = 0;
    let doubled = 0;
    // labeled statements / adding block to it ;)
    $: {
        console.log(`printing the count: ${count}`);
        if (count == 10) {
            alert("Damn this count is high, lets reset it.");
            count = 0;
            doubled = 0;
        }
        doubled = count * 2;
    }

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
