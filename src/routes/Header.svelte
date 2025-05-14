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





<!--{#if num.height >= 0}
        <section>
            {#if num.height >= 0}
            <p>{num.height}</p>
        <div
        id={String(num.id)}
        class="w-8 rounded-xl mx-2 shadow-[-5px_-5px_lightgray] duration-1000 hover:shadow-[-5px_-5px_darkgray]"
        style="height: {num.height}px; background-color: {num.color}"
        >
        </div>
        {:else}
        <div
        id={String(num.id)}
        class="w-8 rounded-xl mx-2 shadow-[-5px_-5px_lightgray] duration-1000 hover:shadow-[-5px_-5px_darkgray]"
        style="height: {num.height * -1}px; background-color: {num.color}"
        >
        </div>
        <p>{num.height}</p>
        {/if}
        </section>
        {:else}
        <div class=""></div>
        /if-->