<script lang="ts">
    import { twMerge } from 'tailwind-merge';
	        type bar =
                {
		            gain: number;
		            loss?: number;
		            active: boolean;
	            }
	let {
		metrics,
		title,
		value,
        hasNegativeValues,
		positiveBarActiveClass = 'bg-yellow-500',
		negativeBarActiveClass = 'bg-red-200',
		barColor
	}: {
		metrics: Array<bar>;
		title: string;
		value: string;
        hasNegativeValues: boolean;
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
					<div
						class="w-3 rounded-xl mx-2 {twMerge(bar.active ? positiveBarActiveClass : barColor)}"
						style="height: {bar.gain}px"
					></div>
				</div>
			{/each}
		</div>
		<div class="flex flex-row items-start max-h-screen">
			{#each metrics as bar}
				<div class="flex flex-col align-middle mt-0">
					<div
						class="w-3 rounded-xl mx-2 {twMerge(
							bar.active ? negativeBarActiveClass : barColor
						)} h-auto"
						style="height: {bar.loss}px"
					></div>
				</div>
			{/each}
		</div>
	</div>
</div>
