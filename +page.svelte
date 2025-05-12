<script>
	import Charts from './Charts.svelte';
</script>

<Charts
	metrics={[
		{ gain: 35, positiveActive: false, typeOfChart:'engagement'},
		{ gain: 69, positiveActive: true, typeOfChart:'engagement'},
		{ gain: 12, positiveActive: true, typeOfChart:'engagement'},
		{ gain: 94, positiveActive: false, typeOfChart:'engagement'},
		{ gain: 49, positiveActive: false, typeOfChart:'engagement'},
		{ gain: 67, positiveActive: true, typeOfChart:'engagement'},
		{ gain: 18, positiveActive: true, typeOfChart:'engagement'},
		{ gain: 30, positiveActive: false, typeOfChart:'engagement'}
	]}
	title="Engagement"
	value="+46%"
	positiveBarActiveClass="bg-yellow-500"
	negativeBarActiveClass="bg-red-800"
	barColor="bg-gray-300"
	rotateDegree={30}
/>
<Charts
	metrics={[
		{ gain: 95, loss: 38, positiveActive: true, negativeActive: false, typeOfChart:'followers' },
		{ gain: 34, loss: 29, positiveActive: true, negativeActive: false, typeOfChart:'followers' },
		{ gain: 39, loss: 12, positiveActive: false, negativeActive: true, typeOfChart:'followers' },
		{ gain: 84, loss: 18, positiveActive: true, negativeActive: false, typeOfChart:'followers' },
		{ gain: 56, loss: 83, positiveActive: false, negativeActive: false, typeOfChart:'followers' },
		{ gain: 84, loss: 11, positiveActive: true, negativeActive: true, typeOfChart:'followers' },
		{ gain: 18, loss: 15, positiveActive: false, negativeActive: true, typeOfChart:'followers' },
		{ gain: 60, loss: 67, positiveActive: false, negativeActive: false, typeOfChart:'followers' }
	]}
	title="Followers"
	value="+25%"
	positiveBarActiveClass="bg-green-600"
	negativeBarActiveClass="bg-red-400"
	barColor="bg-gray-300"
	rotateDegree={-20}
/>
