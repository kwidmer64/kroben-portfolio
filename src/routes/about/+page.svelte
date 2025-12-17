<script lang="ts">
	import TechComponent from './TechComponent.svelte';

	let props = [
		{
			name: "Java",
			color: "#111111",
			path: "java"
		},
		{
			name: "C#",
			color: "#222222",
			path: "csharp"
		},
		{
			name: "TypeScript",
			color: "#333",
			path: "typescript"
		},
		{
			name: "React",
			color: "#333",
			path: "react"
		},
		{
			name: "Svelte",
			color: "#333",
			path: "svelte"
		},
	]
</script>

<h1 class="text-5xl text-center font-bold mt-10">About Me</h1>

<div class="flex justify-center mt-10">
<!-- About text -->
	<div class="max-w-1/3 ms-auto border-t-2 pt-10 me-5">
		<p class="text-right">
			Hi! I'm Korben. A software developer from New Jersey. My love for technology started when I was around 7 years old.
			My dad gave me some old computer components and helped me put together my first computer.
			It sat on an old cardboard box for a case, and didn't even have a power button (I had to jump the pins with a paper clip to start it).
			Since then I've explored a bunch of different languages but ultimately found the object oriented ones to be my favorite (though I work in JavaScript quite a lot)!
			You can find some of these languages and libraries to the right. Click the button below to view some of my work!
		</p>
	</div>
<!-- Tech Stack -->
	<div class="w-1/2 flex justify-around flex-wrap gap-10 px-5">
		{#each props as tech (tech.name)}
			<TechComponent {tech} />
		{/each}
	</div>
</div>