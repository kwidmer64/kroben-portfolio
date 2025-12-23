<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import '@fontsource/montserrat';
	import '@fortawesome/fontawesome-free/css/all.min.css'

	let { children } = $props();

	function handleNavHover(event: MouseEvent) {
		const hovered = event.currentTarget as HTMLElement;
		const sibling = hovered.nextElementSibling; // returns the element immediately following the current one in the parent's children list

		// check for truthy value (sibling exists and nextElementSibling did not return null)
		if (sibling) {
			sibling.classList.toggle("link-hovered");
		}
	}

	// MOBILE NAVBAR
	// let showNav: boolean = false;
	//
	// function toggleNav() {
	// 	showNav = !showNav;
	// }
</script>

<style>
		/*noinspection CssUnusedSymbol*/
    :global(.link-hovered) {
				opacity: 1 !important;
		}

    .link-block {
        opacity: 0;
        transition: opacity 0.2s;
        height: 30%;
        width: 100%;
        background-color: #FFA400;
        position: absolute;
        bottom: 0.25rem;
        left: 0;
        right: 0;
        margin: 0 auto;
        filter: blur(2px);
        border-radius: 50%;
    }
</style>

<!--<svelte:head>-->
<!--	<link rel="icon" href={favicon} />-->
<!--</svelte:head>-->

<div class="flex flex-col min-h-[100vh]">
	<nav class="h-20 flex justify-between relative top-0 z-10">
		<a href="/" class="w-1/2 text-3xl font-bold h-full flex items-center justify-start pl-7 lg:pl-20">KW</a>
		<!-- Desktop Nav -->
		<div class="w-4xl flex justify-around items-center z-0">
			<div class="relative">
				<a href="/" class="text-neutral-100 z-20 relative" onmouseenter={handleNavHover} onmouseleave={handleNavHover}>Home</a>
				<div class="link-block z-10"></div>
			</div>
			<div class="relative">
				<a href="/projects" class="text-neutral-100 z-20 relative" onmouseenter={handleNavHover} onmouseleave={handleNavHover}>Projects</a>
				<div class="link-block z-10"></div>
			</div>
			<div class="relative">
				<a href="/experience" class="text-neutral-100 z-20 relative" onmouseenter={handleNavHover} onmouseleave={handleNavHover}>Experience</a>
				<div class="link-block z-10"></div>
			</div>
		</div>
	</nav>

	<main class="flex-1">
		{@render children?.()}
	</main>

	<footer class="flex flex-col justify-center items-center gap-2 h-20 bg-zinc-900 text-zinc-500 bottom-0 left-0 right-0 relative">
		<ul class="flex gap-4 underline decoration-dotted">
			<li>
				<a href="https://github.com/kwidmer64">GitHub</a>
			</li>
			<li>
				<a href="https://linkedin.com/in/kwidmer">LinkedIn</a>
			</li>
		</ul>

		<p class="text-sm">Developed by Korben Widmer - Copyright 2025 - All Rights Reserved</p>
	</footer>
</div>