<script>
	import Charts from './Charts.svelte';
</script>

<Charts
	bars={[
		[35, false],
		[69, true],
		[12, true],
		[94, false],
		[49, false],
		[67, true],
		[18, true],
		[30, false]
	]}
	title="Engagement"
	value="+46%"
	do_neg_bars={false}
	negative_bars={[]}
	active_col_pos="bg-yellow-500"
	active_col_neg="bg-red-200"
	nonactive_col="bg-gray-300"
/>
<br />
<br />
<br />
<br />
<br />
<br />
<Charts
	bars={[
		[98, true],
		[18, false],
		[38, false],
		[89, true],
		[34, false],
		[75, true],
		[21, true],
		[85, false]
	]}
	title="Followers"
	value="+25%"
	do_neg_bars={true}
	negative_bars={[
		[15, false],
		[78, false],
		[67, true],
		[45, true],
		[99, true],
		[85, false],
		[21, true],
		[77, true]
	]}
	active_col_pos="bg-green-600"
	active_col_neg="bg-red-200"
	nonactive_col="bg-gray-300"
/>
