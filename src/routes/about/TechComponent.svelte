<script lang="ts">
	const { tech } = $props();
</script>

<div class="w-55 h-70 border-4 rounded-lg flex flex-col justify-center items-center gap-3" style:border-color={tech.color}>
	{#await import(`$lib/assets/about/tech/${tech.path}.png`) then { default: src }}
		<img {src} alt="alt" class="max-w-2/3"/>
	{/await}
	<p class="text-lg font-semibold">{tech.name}</p>
</div>