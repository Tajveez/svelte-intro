<script>
    let x = 5;
</script>

{#if x > 10}
    <p>{x} is greater than 10</p>
{:else if x < 5}
    <p>{x} is less than 5</p>
{:else}
    <p>{x} is is in between 5 - 10</p>
{/if}
