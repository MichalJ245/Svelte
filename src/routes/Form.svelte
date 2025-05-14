<script>
    let {less, more} = $props();
</script>
<style>
    button
    {
        background-color: blue;
        color: white;
        border-radius: 10px;
        padding: 5px;
    }
</style>
<button onclick={less}>-1</button>
<button onclick={more}>+1</button>