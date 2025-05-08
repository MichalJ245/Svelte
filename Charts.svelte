<script lang="ts">
	let {
		bars,
		title,
		value,
		n_active_bar_id,
        negative_bars = [],
        n_active_neg_bar = [],
        active_col_pos,
        active_col_neg,
        nonactive_col
	}: { bars: number[]; title: string; value: string; n_active_bar_id: number[]; negative_bars: number[]; n_active_neg_bar: number[]; active_col_pos: string; active_col_neg: string; nonactive_col: string} = $props();
</script>

<div id="main" class="max-w-max max-h-screen flex flex-col mx-auto shadow-2xl rounded-[50px] p-10 border-solid border-1 border-gray-200 outline-10 outline-white">
	<h1 class="font-bold text-2xl text-left">{title}</h1>
	<p class="text-left p-1 bg-green-200 rounded-xl w-14 text-green-700 font-semibold">{value}</p>
	<div id="wykres" class="flex flex-col max-h-screen">
		<div class="flex flex-row items-end max-h-screen">
			{#each bars as bar, i}
				<div class="flex flex-col align-middle mt-0">
						{#if !n_active_bar_id.includes(i+1)}
							<div class="w-3 rounded-xl mx-2 {active_col_pos}" style="height: {bar}px"></div>
						{:else}
							<div class="w-3 rounded-xl mx-2 {nonactive_col}" style="height: {bar}px"></div>
						{/if}
						<div class="w-3 mx-2 h-2"></div>
				</div>
			{/each}
		</div>
		<div class="flex flex-row items-start max-h-screen">
            {#if negative_bars.length !== 0}
			{#each negative_bars as bar, i}
				<div class="flex flex-col align-middle mt-0">
					{#if !n_active_neg_bar.includes(i+1)}
						<div class="w-3 rounded-xl mx-2 {active_col_neg} h-auto" style="height: {bar * -1}px"></div>
					{:else}
                        <div class="w-3 rounded-xl mx-2 {nonactive_col} h-auto" style="height: {bar * -1}px"></div>
					{/if}
				</div>
			{/each}
            {/if}
		</div>
	</div>
</div>