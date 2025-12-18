<script lang="ts">
export let title: string = '';
export let icons: Icon[];
export let href: string = '#';
export let image: string = '';

type Icon = {
	static: string;
	hovered: string;
}

let isHovered = false;
</script>

<a href={href}
	 class="project"
	 on:mouseenter={() => isHovered = true}
	 on:mouseleave={() => isHovered = false}
>
	<div class="border-4 border-zinc-800 hover:border-zinc-200 rounded-lg p-4 pb-0 pl-6 min-h-50 grid grid-rows-4 relative overflow-clip transition-colors duration-150">
		<h2 class="text-3xl font-bold">{title}</h2>
		<p class="row-span-2 font-medium">
			<slot />
		</p>
		<div class="flex h-7 gap-4">
			{#each icons as icon (icon.static)}
				<img src={isHovered ? icon.hovered : icon.static}/>
			{/each}
		</div>

		<img src={image} alt="Tide prediction website" class="absolute left-0 w-full h-full object-cover -z-1 scale-110 md:scale-125 blur-sm brightness-50 {isHovered ? 'grayscale-0' : 'grayscale-75'}"/>
	</div>
</a>