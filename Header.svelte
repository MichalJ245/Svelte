<script>
    let {value = "Hello there"} = $props();
</script>
<style>
    h1
    {
        font-weight: bold;
        font-size: 25px;
        text-align: center;
    }
</style>
<h1>{value}</h1>