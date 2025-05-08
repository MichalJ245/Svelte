<script lang="ts">
	type bar = {
		gain: number;
		loss: number;
		active: boolean;
	};
	let {
		metrics,
		title,
		value,
		positiveBarActiveClass = 'bg-yellow-500',
		negativeBarActiveClass = 'bg-red-200',
		barColor
	}: {
		metrics: Array<bar>;
		title: string;
		value: string;
		positiveBarActiveClass: string;
		negativeBarActiveClass: string;
		barColor: string;
	} = $props();
</script>

<div
	id="main"
	class="max-w-max max-h-screen flex flex-col mx-auto shadow-2xl rounded-[50px] p-10 border-solid border-1 border-gray-200 outline-10 outline-white mb-10"
>
	<h1 class="font-bold text-2xl text-left">{title}</h1>
	<p class="text-left p-1 bg-green-100 rounded-xl w-14 text-green-700 font-semibold">{value}</p>
	<div id="wykres" class="flex flex-col max-h-screen">
		<div class="flex flex-row items-end max-h-screen">
			{#each metrics as bar}
				<div class="flex flex-col align-middle mt-0">
					{#if bar.active}
						<div
							class="w-3 rounded-xl mx-2 {positiveBarActiveClass}"
							style="height: {bar.gain}px"
						></div>
					{:else}
						<div class="w-3 rounded-xl mx-2 {barColor}" style="height: {bar.gain}px"></div>
					{/if}
					<div class="w-3 mx-2 h-2"></div>
				</div>
			{/each}
		</div>
		<div class="flex flex-row items-start max-h-screen">
			{#each metrics as bar}
				<div class="flex flex-col align-middle mt-0">
					{#if bar.active}
						<div
							class="w-3 rounded-xl mx-2 {negativeBarActiveClass} h-auto"
							style="height: {bar.loss}px"
						></div>
					{:else}
						<div class="w-3 rounded-xl mx-2 {barColor} h-auto" style="height: {bar.loss}px"></div>
					{/if}
				</div>
			{/each}
		</div>
	</div>
</div>
