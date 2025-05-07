<script>
    //import
    import Column from './Column.svelte';
    import Header from './Header.svelte';
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
#main
{
    width: 100%;
    height: 100vh;
    display: flex;
    align-items: center;
    flex-direction: column;
}
input
{
    border: 1px solid black;
}
#wykres
{
    display: flex;
    flex-direction: column;
    height: 328px;
    width: 300px;
}
#wykres > div
{
    display: flex;
    flex-direction: row;
    align-items: flex-end;
    height: 164px;
    border-bottom: 1px solid black;
}
#wykres > div:last-child
{
    align-items: flex-start;
}
.column
{
    display: flex;
    flex-direction: column;
    vertical-align: middle;
    align-items: center;
    margin-top: 0;
}
input[type="button"]
{
    width: 100px;
    height: 40px;
    background-color: blue;
    color: white;
    vertical-align: middle;
    border: none;
    border-radius: 15px;
    margin: 0 10px;
    font-size: 30px;
    font-weight: bold;
}
.color
{
    width: 50px;
    height: 50px;
    border-radius: 50%;
    margin: 0 10px;
}
button[aria-current=true]
{
    box-shadow: 2px 2px gray;
    transition: 0.5s;
}
.placeholder
{
    width: 30px;
    height: 10px;
    margin: 0 10px;
}
</style>
<div id="main">
<Header value={header} />
<div id="wykres">
<div>
{#each num_of_val as num}
    <div class="column">
        {#if num.height >= 0}
            <Column {...num}/>
        {:else}
        <div class="placeholder"></div>
        {/if}
    </div>
{/each}
</div>
<div>
    {#each num_of_val as num}
    <div class="column">
        {#if num.height < 0}
            <Column {...num}/>
        {:else}
        <div class="placeholder"></div>
        {/if}
    </div>
    {/each}
</div>
</div>
<label for="h">Treść nagłówka&nbsp;</label><input type="text" id="h" bind:value={header}><br>
<label for="nov">Ilość słupków&nbsp;</label><section id="nov"><input type="button" value="+" onclick={more_columns}><input type="button" value="-" onclick={less_columns}></section>
<label for="hoch">Wysokość słupka&nbsp;</label><section id="hoch"><input type="number" bind:value={hoeche} min="-100" max="100"><input type="range" bind:value={hoeche} min="-100" max="100"></section>
<label for="color">Wybierz kolor słupka</label>
<section id="color">
{#each colors as color}
<button
style="background-color: {color}"
class="color"
aria-label={color}
aria-current={select === color}
onclick={() => select = color}
>
</button>
{/each}
</section>
</div>