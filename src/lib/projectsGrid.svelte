<script lang="ts">
	import tidesImg from '$lib/assets/projects/tidesImg.jpg';
	import portfolioImg from '$lib/assets/projects/portfolioImg.jpg';
	import icons from '$lib/icons.ts';
	import Project from '$lib/projectIndividual.svelte';

	// get each project div on the page
	// on hover, add the classes for shadow and text color
	// on mouse leave, remove those classes
</script>

<div class="flex flex-col lg:grid lg:grid-cols-2 px-10 sm:px-60 lg:px-40 gap-4">
	<h1 class="text-5xl font-bold col-span-2 mb-6">Projects</h1>

	<Project title="Tides" icons={[icons.react, icons.js, icons.nodejs]} href="https://tides.kroben.net/" image={tidesImg}>
		<p>A simple web app that displays the tides for a specified location.
			Uses an Azure Function to contact the Maps.co geocoding API.
			Then gets tide predictions data from the NOAA Tides & Currents API</p>
	</Project>

	<Project title="Portfolio" icons={[icons.svelte, icons.ts]} href="/" image={portfolioImg}>
		<p>My personal portfolio which contains information about me, my projects, and my experience.
			I eventually would like to experiment with moving some of the data into a database to work on my database skills!</p>
	</Project>
</div>