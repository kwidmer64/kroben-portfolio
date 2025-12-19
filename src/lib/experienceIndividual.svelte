<script lang="ts">
	export let title: string = '', company: string = '', start: string = '', end: string = '';
	export let skills: string[] = [];
</script>

<div class="grid grid-rows-5 2xl:grid-rows-4 gap-2 grow min-h-50 p-4 pl-6 border-2 border-zinc-800 hover:border-[#2E86AB] hover:bg-[#111B2D]/25 rounded-lg overflow-clip z-0 transition-all duration-250 hover:shadow-lg/25 shadow-[#2E86AB] hover:-translate-y-1">
	<h2 class="text-3xl font-bold text-zinc-200">{title}</h2>
	<h3 class="text-xl text-[#2E86AB]">{company}</h3>
	<p class="row-span-3 2xl:row-span-2 font-medium text-zinc-400  border-b-1 border-b-zinc-800">
		<slot />
	</p>
	<div class="flex justify-between min-h-7 gap-4">
		<div>
			Skills: {skills.join(', ')}
		</div>
		<div>
			{start} - {end}
		</div>
	</div>
</div>