<script>
	import Charts from './Charts.svelte';
</script>

<Charts
	bars={[35, 64, 15, 47, 45, 38, 74, 39]}
	title="Engagement"
	value="+46%"
	n_active_bar_id={[1,6]}
    negative_bars={[]}
    n_active_neg_bar={[]}
    active_col_pos="bg-yellow-500"
    active_col_neg="bg-red-200"
    nonactive_col="bg-gray-300"
/>
<br>
<br>
<br>
<br>
<br>
<br>
<Charts
	bars={[78, 9, 57, 45, 98, 67, 56, 30]}
	title="Followers"
	value="+25%"
	n_active_bar_id={[5,6]}
	negative_bars={[-30, -54, -12, -47, -68, -62, -84, -31]}
	n_active_neg_bar={[4,7]}
    active_col_pos="bg-green-600"
    active_col_neg="bg-red-200"
    nonactive_col="bg-gray-300"
/>
