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
	 class="project flex hover:-translate-y-2 transition-transform duration-150"
	 on:mouseenter={() => isHovered = true}
	 on:mouseleave={() => isHovered = false}
>
	<div class="grid grid-rows-5 2xl:grid-rows-4 gap-2 grow relative min-h-50 p-4 pl-6 border-4 border-zinc-800 hover:border-zinc-200 rounded-lg overflow-clip transition-colors duration-150 hover:shadow-lg/25 shadow-amber-50">
		<h2 class="text-3xl font-bold">{title}</h2>
		<p class="row-span-3 2xl:row-span-2 font-medium">
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