<script>
    let {id,height,color} = $props();
</script>
<style>
    .column
    {
        background-color: --color;
        width: 30px;
        border-radius: 10px;
        margin: 0 10px;
        box-shadow: -5px -5px lightgray;
    }
    .column:hover
    {
        transition: linear 0.5s;
        box-shadow: -5px -5px darkgray;
    }
    p
    {
        vertical-align: middle;
        text-align: center;
    }
</style>
<section>
    
    {#if height >= 0}
    <p>{height}</p>
<div
id={String(id)}
class="column"
style="height: {height}px; background-color: {color}"
>
</div>
{:else}
<div
id={String(id)}
class="column"
style="height: {height * -1}px; background-color: {color}"
>
</div>
<p>{height}</p>
{/if}
</section>