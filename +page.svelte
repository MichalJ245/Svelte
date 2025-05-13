<script lang="ts">
	import { twMerge } from 'tailwind-merge';
	import Charts from './Charts.svelte';
	let button1Active = $state(true);
	let button2Active = $state(true);
	const basicClassesFrame = ' w-12 rounded-[20px] h-6 transition-all duration-300';
	const circle =
		'w-5 bg-gray-100 h-5 mx-1 my-auto rounded-[50px] transition-transform duration-300';
	function getFrameStyle(button: boolean) {
		return twMerge(basicClassesFrame, button ? 'bg-blue-500' : 'bg-gray-500');
	}
	function circleMove(button: boolean) {
		return twMerge(circle, button ? 'translate-0' : 'translate-x-[18px]');
	}
</script>

<Charts
	metrics={[
		{ gain: 35, positiveActive: false },
		{ gain: 69, positiveActive: true },
		{ gain: 12, positiveActive: true },
		{ gain: 94, positiveActive: false },
		{ gain: 49, positiveActive: false },
		{ gain: 67, positiveActive: true },
		{ gain: 18, positiveActive: true },
		{ gain: 30, positiveActive: false }
	]}
	type="engagement"
	title="Engagement"
	value="+46%"
	positiveBarActiveClass="bg-yellow-500"
	negativeBarActiveClass="bg-red-800"
	barColor="bg-gray-300"
	rotateDegree={button1Active ? 10 : 20}
/>
<div class="flex justify-center mb-20">
<button
	aria-label="rotate"
	onclick={() => (button1Active = !button1Active)}
	class={getFrameStyle(button1Active)}><div class={circleMove(button1Active)}></div></button
>
</div>
<Charts
	metrics={[
		{ gain: 95, loss: 38, positiveActive: true, negativeActive: false },
		{ gain: 34, loss: 29, positiveActive: true, negativeActive: false },
		{ gain: 39, loss: 12, positiveActive: false, negativeActive: true },
		{ gain: 84, loss: 18, positiveActive: true, negativeActive: false },
		{ gain: 56, loss: 83, positiveActive: false, negativeActive: false },
		{ gain: 84, loss: 11, positiveActive: true, negativeActive: true },
		{ gain: 18, loss: 15, positiveActive: false, negativeActive: true },
		{ gain: 60, loss: 67, positiveActive: false, negativeActive: false }
	]}
	type="followers"
	title="Followers"
	value="+25%"
	positiveBarActiveClass="bg-green-600"
	negativeBarActiveClass="bg-red-400"
	barColor="bg-gray-300"
	rotateDegree={button2Active ? 10 : 20}
/>
<div class="flex justify-center mb-20">
<button
	aria-label="rotate"
	onclick={() => (button2Active = !button2Active)}
	class={getFrameStyle(button2Active)}><div class={circleMove(button2Active)}></div></button
>
</div>