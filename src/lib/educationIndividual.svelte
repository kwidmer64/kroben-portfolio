<script lang="ts">
	export let major: string = '', school: string = '', start: string = '', end: string = '';
	export let coursework: string[] = [];
</script>

<div class="grid grid-rows-5 2xl:grid-rows-4 gap-2 grow min-h-50 p-4 pl-6 border-2 border-zinc-800 hover:border-[#963484] hover:bg-[#2E1028]/25 rounded-lg overflow-clip z-0 transition-all duration-250 hover:shadow-lg/25 shadow-[#963484] hover:-translate-y-1">
	<h2 class="text-3xl font-bold text-zinc-200">{major}</h2>
	<h3 class="text-xl text-[#963484]">{school}</h3>
	<p class="row-span-3 2xl:row-span-2 font-medium text-zinc-400 border-b-1 border-b-zinc-800">
		<slot />
	</p>
	<div class="flex justify-between min-h-7 gap-4">
		<div>
			Relevant Coursework: {coursework.join(', ')}
		</div>
		<div class="text-right">
			{start}{#if end} - {end}{/if}
		</div>
	</div>
</div>