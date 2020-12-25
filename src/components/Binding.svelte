<script>
    import marked from "marked";

    let name = "World";
    let a = 1;
    let b = 1;
    let isChecked = false;

    let weapon = 1;
    let powers = ["Earth Bending"];

    let allPowers = [
        "Earth Bending",
        "Air Bending",
        "Fire Bending",
        "Water Bending",
    ];

    let value = `Some words are *italic*, some are **bold**`;
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

<!-- Grouped Binding -->
<h2>Weapons</h2>
<label> <input type="radio" bind:group={weapon} value={1} /> Mace </label>

<label> <input type="radio" bind:group={weapon} value={2} /> Sword </label>

<label> <input type="radio" bind:group={weapon} value={3} /> Spear </label>

<h2>Powers</h2>
{#each allPowers as _power}
    <label>
        <input type="checkbox" value={_power} bind:group={powers} />
        {_power}
    </label>
{/each}

{#if powers.length === 0}
    <p>Select your weapon and power</p>
{:else if powers.length > weapon}
    <p>You can't have a Dangerous weapon and these Powers at the same time.</p>
{:else}
    <p>Your selected power are {powers.join(', ')}</p>
{/if}

<!-- TextArea Binding -->
<textarea bind:value />
{@html marked(value)}
