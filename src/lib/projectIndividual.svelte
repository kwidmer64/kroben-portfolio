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
	 class="project flex hover:-translate-y-1 transition-transform duration-250"
	 on:mouseenter={() => isHovered = true}
	 on:mouseleave={() => isHovered = false}
>
	<div class="grid grid-rows-5 2xl:grid-rows-4 gap-2 grow relative min-h-50 p-4 pl-6 border-2 border-zinc-800 hover:border-[#FFA400] rounded-lg overflow-clip z-0 transition-all duration-250 hover:shadow-lg/25 shadow-[#FFA400]">
		<h2 class="text-3xl font-bold text-zinc-100">{title}</h2>
		<p class="row-span-3 2xl:row-span-2 font-medium text-[#E29300]">
			<slot />
		</p>
		<div class="flex h-7 gap-4">
			{#each icons as icon (icon.static)}
				<img src={isHovered ? icon.hovered : icon.static}/>
			{/each}
		</div>

		<img src={image} alt="Tide prediction website" class="absolute left-0 w-full h-full object-cover -z-1 scale-110 md:scale-125 blur-sm {isHovered ? 'brightness-30' : 'brightness-15'} grayscale-100"/>
	</div>
</a>