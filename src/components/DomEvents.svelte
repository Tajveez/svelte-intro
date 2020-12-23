<script>
    import { createEventDispatcher } from "svelte";

    let m = {
        x: 0,
        y: 0,
    };

    function handleMouseMove(e) {
        m.x = e.clientX;
        m.y = e.clientY;
    }

    const dispatch = createEventDispatcher();

    function fireDispatch() {
        dispatch("communicate", {
            text: "This is a special msg!",
        });
    }
</script>

<style>
    div {
        width: 100%;
        height: 100%;
        background-color: aquamarine;
        border: 2px solid;
        padding: 20px;
    }
</style>

<div on:mousemove={handleMouseMove}>
    Mouse movement of component is at x:
    {m.x}
    and y:{m.y}
</div>

<button
    on:click|once={(e) => {
        alert('Clicked once.');
    }}>
    i can be clicked once!
</button>

<button on:click={fireDispatch}> click to dispatch </button>
