<script>
    import Login from "./Login.svelte";
    export let name = "User?";
    export let age = "00";
    export let profession = "None";
</script>

<style>
    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }
</style>

<div>
    <Login />
    <h1>Hello {name}!</h1>
    <p>Age: {age}</p>
    <p>profession: {profession}</p>
</div>
