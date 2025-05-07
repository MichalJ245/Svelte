<script>
    //tablica kolorów
    const colors = ["red","green","blue","yellow","pink","black","orange","purple","magenta"];
    let select = $state(colors[0]);
    let header = $state("Header");
    //słupki
    let num_of_val = $state([
        {id: 1,height: 87,color: "red"},
        {id: 2,height: -45,color: "blue"},
        {id: 3,height: 18, color: "orange"}
    ]);
    let hoeche =$state(100);
    //dodawanie i usuwanie słupków
    function more_columns()
    {
        num_of_val.push({id:num_of_val.length+1,height:hoeche,color:select});
        //num_of_val.length+1;
    }
    function less_columns()
    {
        num_of_val.pop();
        num_of_val.length-1;
    }
</script>
<style>
button[aria-current=true]
{
    box-shadow: 2px 2px gray;
    transition: 0.5s;
}
</style>
<div id="main" class="max-w-max max-h-screen flex flex-col items-center justify-center mx-auto">
<h1 class="font-bold text-2xl text-center">{header}</h1>
<div id="wykres" class="flex flex-col max-h-screen">
<div class="flex flex-row items-end max-h-screen border-black border-solid border-b">
{#each num_of_val as num}
    <div class="flex flex-col align-middle mt-0">
        {#if num.height >= 0}
        <p class="text-center">{num.height}</p>
        <div
        id={String(num.id)}
        class="w-8 rounded-xl mx-2 shadow-[-5px_-5px_lightgray] duration-1000 hover:shadow-[-5px_-5px_darkgray] bg-{num.color}"
        style="height: {num.height}px; background-color: {num.color}"
        >
        </div>
        {:else}
        <div class="w-8 mx-2 h-2"></div>
        {/if}
    </div>
{/each}
</div>
<div class="flex flex-row items-start max-h-screen">
    {#each num_of_val as num}
    <div class="flex flex-col align-middle mt-0">
        {#if num.height <= 0}
        <div
        id={String(num.id)}
        class="w-8 rounded-xl mx-2 shadow-[-5px_-5px_lightgray] duration-1000 hover:shadow-[-5px_-5px_darkgray] bg-{num.color}"
        style="height: {num.height*-1}px; background-color: {num.color}"
        >
        </div>
        <p class="text-center">{num.height}</p>
        {:else}
        <div class="w-8 mx-2 h-2"></div>
        {/if}
    </div>
    {/each}
</div>
</div>
<label for="h">Treść nagłówka&nbsp;</label><input type="text" id="h" bind:value={header} class="border-black border-solid border-1"><br>
<label for="nov">Ilość słupków&nbsp;</label><section id="nov"><input type="button" value="+" onclick={more_columns} class="w-24 h-8 bg-blue-700 text-white border-none rounded-2xl mx-2 text-2xl font-bold"><input type="button" value="-" onclick={less_columns} class="w-24 h-8 bg-blue-700 text-white border-none rounded-2xl mx-2 text-2xl font-bold"></section>
<label for="hoch">Wysokość słupka&nbsp;</label><section id="hoch"><input type="number" bind:value={hoeche} min="-100" max="100" class="border-black border-solid border-1"><input type="range" bind:value={hoeche} min="-100" max="100"></section>
<label for="color">Wybierz kolor słupka</label>
<section id="color">
{#each colors as color}
<button
style="background-color: {color}"
class="w-12 h-12 rounded-3xl mx-2"
aria-label={color}
aria-current={select === color}
onclick={() => select = color}
>
</button>
{/each}
</section>
</div>