<script>
    let name = "World";
    let a = 1;
    let b = 1;
    let isChecked = false;
</script>

<input bind:value={name} />
<h3>{name}</h3>

<label>
    <input type="number" bind:value={a} min="-10" max="100" />
    <input type="range" bind:value={a} min="-10" max="100" />
</label>

<label>
    <input type="number" bind:value={b} min="-10" max="100" />
    <input type="range" bind:value={b} min="-10" max="100" />
</label>

<p>{a} + {b} = {a + b}</p>

<label>
    <input type="checkbox" bind:checked={isChecked} />
    <button disabled={!isChecked}>Start</button>
</label>
{#if isChecked}
    <p>Hurray!!!</p>
{:else}
    <p>Booooo!!!</p>
{/if}
