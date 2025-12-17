<script>
	import tidesImg from '$lib/assets/projects/tidesImg.jpg';
	import portfolioImg from '$lib/assets/projects/portfolioImg.jpg';

	// get each project div on the page
	// on hover, add the classes for shadow and text color
	// on mouse leave, remove those classes
</script>

<div class="grid grid-cols-2 mt-10 px-60 gap-4">
	<h1 class="text-5xl font-bold col-span-2 mb-6">Projects</h1>
	<a href="https://tides.kroben.net/">
		<div class="border-4 border-sky-600 rounded-lg p-4 pb-0 pl-6 h-50 grid grid-rows-4 relative overflow-clip">
			<h2 class="text-3xl font-bold">Tides</h2>
			<p class="row-span-2 font-medium">A simple web app that displays the tides for a specified location.
				Uses an Azure Function to contact the Maps.co geocoding API.
				Then gets tide predictions data from the NOAA Tides & Currents API</p>
			<p class="font-light text-gray-300">Technologies: React, JavaScript, Azure Functions</p>

			<img src={tidesImg} alt="Tide prediction website" class="absolute -top-1/2 left-0 w-full object-cover -z-1 blur-sm brightness-50"/>
		</div>
	</a>

	<a href="/">
		<div class="border-4 border-amber-600 rounded-lg p-4 pb-0 pl-6 h-50 grid grid-rows-4 relative overflow-clip">
			<h2 class="text-3xl font-bold">Portfolio</h2>
			<p class="row-span-2 font-medium">My personal portfolio which contains information about me, my projects, and my experience.
				I eventually would like to experiment with moving some of the data into a database to work on my database skills!</p>
			<p class="font-light text-gray-300">Technologies: Svelte, TypeScript</p>

			<img src={portfolioImg} alt="Tide prediction website" class="absolute -top-1/2 left-0 w-full object-cover -z-1 blur-sm brightness-50"/>
		</div>
	</a>
</div>
