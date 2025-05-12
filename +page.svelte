<script>
	import Charts from './Charts.svelte';
</script>

<Charts
	metrics={[
		{ gain: 35, positiveActive: false},
		{ gain: 69, positiveActive: true},
		{ gain: 12, positiveActive: true},
		{ gain: 94, positiveActive: false},
		{ gain: 49, positiveActive: false},
		{ gain: 67, positiveActive: true},
		{ gain: 18, positiveActive: true},
		{ gain: 30, positiveActive: false}
	]}
	type="engagement"
	title="Engagement"
	value="+46%"
	positiveBarActiveClass="bg-yellow-500"
	negativeBarActiveClass="bg-red-800"
	barColor="bg-gray-300"
	rotateDegree={30}
/>
<Charts
	metrics={[
		{ gain: 95, loss: 38, positiveActive: true, negativeActive: false},
		{ gain: 34, loss: 29, positiveActive: true, negativeActive: false},
		{ gain: 39, loss: 12, positiveActive: false, negativeActive: true},
		{ gain: 84, loss: 18, positiveActive: true, negativeActive: false},
		{ gain: 56, loss: 83, positiveActive: false, negativeActive: false},
		{ gain: 84, loss: 11, positiveActive: true, negativeActive: true},
		{ gain: 18, loss: 15, positiveActive: false, negativeActive: true},
		{ gain: 60, loss: 67, positiveActive: false, negativeActive: false}
	]}
	type="followers"
	title="Followers"
	value="+25%"
	positiveBarActiveClass="bg-green-600"
	negativeBarActiveClass="bg-red-400"
	barColor="bg-gray-300"
	rotateDegree={-20}
/>
