<script lang="ts">
    let {slupki,title,value,active_bar_id} : {slupki: number[],title:string,value:string,active_bar_id:number} = $props()
</script>
<div id="main" class="max-w-max max-h-screen flex flex-col mx-auto">
<h1 class="font-bold text-2xl text-left">{title}</h1>
<p class="text-left p-2 bg-green-200 rounded-xl w-14">{value}</p>
<div id="wykres" class="flex flex-col max-h-screen">
<div class="flex flex-row items-end max-h-screen">
{#each slupki as slupek,i}
    <div class="flex flex-col align-middle mt-0">
        {#if slupek > 0}
        {#if active_bar_id == i}
        <div
        class="w-2 rounded-xl mx-2 bg-yellow-500"
        style="height: {slupek}px"
        >
        </div>
        {:else}
        <div
        class="w-2 rounded-xl mx-2 bg-gray-500"
        style="height: {slupek}px"
        >
        </div>
        {/if}
        {:else}
        <div class="w-2 mx-2 h-2"></div>
        {/if}
    </div>
{/each}
</div>
<div class="flex flex-row items-start max-h-screen">
    {#each slupki as slupek}
    <div class="flex flex-col align-middle mt-0">
        {#if slupek < 0}
        <div
        class="w-2 rounded-xl mx-2 bg-gray-500"
        style="height: {slupek*-1}px"
        >
        </div>
        {:else}
        <div class="w-2 mx-2 h-2"></div>
        {/if}
    </div>
    {/each}
</div>
</div>
</div>