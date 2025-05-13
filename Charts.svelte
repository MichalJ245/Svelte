<script lang="ts">
	import { twMerge } from 'tailwind-merge';
	const {
		title,
		value,
		positiveBarActiveClass = 'bg-yellow-500',
		negativeBarActiveClass = 'bg-red-200',
		barColor,
		type,
		metrics,
		rotateDegree
	}:
		| {
				type: 'followers';
				metrics: Array<{
					gain: number;
					loss: number;
					positiveActive: boolean;
					negativeActive: boolean;
				}>;
				title: string;
				value: string;
				positiveBarActiveClass: string;
				negativeBarActiveClass: string;
				barColor: string;
				rotateDegree: number;
		  }
		| {
				type: 'engagement';
				metrics: Array<{ gain: number; positiveActive: boolean }>;
				title: string;
				value: string;
				positiveBarActiveClass: string;
				negativeBarActiveClass: string;
				barColor: string;
				rotateDegree: number;
		  } = $props();
const basicClasses = "mt-0 w-3 rounded-xl mx-2 h-auto";
function ActiveBarColor(barNegative: boolean, colorActive: string)
{
	return twMerge(basicClasses,barNegative ? colorActive : barColor)
}
	
</script>

<div
	id="main"
	class="max-w-max max-h-screen flex flex-col mx-auto shadow-2xl rounded-[50px] p-10 border-solid border-1 border-gray-200 outline-10 outline-white mb-40"
	style="transform:rotate({rotateDegree}deg);"
>
	<h1 class="font-bold text-2xl text-left">{title}</h1>
	<p class="text-left p-1 bg-green-100 rounded-xl w-14 text-green-700 font-semibold">{value}</p>
	<div class="flex flex-col max-h-screen">
		{#if type === 'followers'}
			<div class="flex flex-row items-end max-h-screen">
				{#each metrics as bar}
					<div
						class={ActiveBarColor(bar.positiveActive, positiveBarActiveClass)}
						style="height: {bar.gain}px"
					></div>
				{/each}
			</div>
			<div class="flex flex-row items-start max-h-screen">
				{#each metrics as bar}
					<div
						class={ActiveBarColor(bar.negativeActive, negativeBarActiveClass)}
						style="height: {bar.loss}px"
					></div>
				{/each}
			</div>
		{:else}
			<div class="flex flex-row items-end max-h-screen">
				{#each metrics as bar}
					<div
						class={ActiveBarColor(bar.positiveActive, positiveBarActiveClass)}
						style="height: {bar.gain}px"
					></div>
				{/each}
			</div>
		{/if}
	</div>
	
</div>
