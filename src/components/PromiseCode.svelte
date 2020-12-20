<script>
    async function getRandomNummber() {
        const res = await fetch("tutorial/random-number");
        const text = await res.text();

        if (res.ok) {
            return text;
        } else {
            throw new Error(text);
        }
    }

    let promise = getRandomNummber();
    function handleClick() {
        promise = getRandomNummber();
    }
</script>

<button on:click={handleClick}> generate a random number </button>
{#await promise}
    <p>... waiting</p>
{:then number}
    <p>value is {number}</p>
{:catch error}
    <p>Error is: {error.message}</p>
{/await}
