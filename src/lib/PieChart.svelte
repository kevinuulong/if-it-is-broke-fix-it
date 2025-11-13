<!-- 
 https://svelte.dev/playground/9dca4b51c5f24f38a2c1ce681a1142c1?version=5.43.6 
 Source for pie charts
-->

<script>
	import * as d3 from "d3";
	
	// Receive plot data as prop.
    let {data} = $props();
	
	// Specify the chart’s dimensions.
	const width = 200;
  const height = 200;

  // Create the pie layout and arc generator.
  const pie = d3.pie()
		.sort(null)
		.value(d => d.value);

  const arcPath = d3.arc()
		// control the style of the pie slices;
		// try changing the inner radius to 100 to see what happens
		.innerRadius(0)
		.outerRadius(Math.min(width, height) / 2 - 1);

  const labelRadius = arcPath.outerRadius()() * 0.6;

  // A separate arc generator for labels.
  const arcLabel = d3.arc()
		.innerRadius(labelRadius)
		.outerRadius(labelRadius);

  const arcs = pie(data);
</script>

<svg
  {width}
  {height}
  viewBox="{-width / 2}, {-height / 2}, {width}, {height}"
  style:max-width="100%"
  style:height="auto"
>

	<g class="data">

		<!-- Loop through the data-slices. -->
		{#each arcs as slice}
			
			<!-- Add each pie-slice. -->
			<path 
				d={arcPath(slice)}
				fill={slice.data.color}
				stroke="white"
			/>

			<!-- Add each label. -->
			<!-- <text
				style="font-weight: bold"
				transform="translate({arcLabel.centroid(slice)})"
				text-anchor="middle"
				>
				{slice.data.name}
			</text> -->
			
			<!-- show the value if there is enough room. -->
			<!-- {#if (slice.endAngle - slice.startAngle) > 0.25}
				<text
					text-anchor="middle"
					transform="translate({[arcLabel.centroid(slice)[0], arcLabel.centroid(slice)[1] + 10]})"
					>
					{slice.data.value.toLocaleString("en-US")}
				</text>
			{/if} -->
		{/each}
	</g>
</svg>

<style>
	svg {
		font-size: 10px;
	}
	aside {
		text-align: center;
	}
</style>