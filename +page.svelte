<script>
	import Charts from './Charts.svelte';
</script>

<Charts
	metrics={[
		{ gain: 35, loss: 0, active: false },
		{ gain: 69, loss: 0, active: true },
		{ gain: 12, loss: 0, active: true },
		{ gain: 94, loss: 0, active: false },
		{ gain: 49, loss: 0, active: false },
		{ gain: 67, loss: 0, active: true },
		{ gain: 18, loss: 0, active: true },
		{ gain: 30, loss: 0, active: false }
	]}
	title="Engagement"
	value="+46%"
	positiveBarActiveClass="bg-yellow-500"
	negativeBarActiveClass="bg-red-200"
	barColor="bg-gray-300"
/>
<Charts
	metrics={[
		{ gain: 95, loss: 38, active: true },
		{ gain: 34, loss: 29, active: true },
		{ gain: 39, loss: 12, active: false },
		{ gain: 84, loss: 18, active: true },
		{ gain: 56, loss: 83, active: false },
		{ gain: 84, loss: 11, active: true },
		{ gain: 18, loss: 98, active: false },
		{ gain: 60, loss: 67, active: false }
	]}
	title="Followers"
	value="+25%"
	positiveBarActiveClass="bg-green-600"
	negativeBarActiveClass="bg-red-200"
	barColor="bg-gray-300"
/>
