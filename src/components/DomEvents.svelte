<script>
    let m = {
        x: 0,
        y: 0,
    };

    function handleMouseMove(e) {
        m.x = e.clientX;
        m.y = e.clientY;
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
