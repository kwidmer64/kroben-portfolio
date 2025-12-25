<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import '@fontsource/montserrat';
	import '@fortawesome/fontawesome-free/css/all.min.css'
	import { onMount } from 'svelte';

	let { children } = $props();

	function handleNavHover(event: MouseEvent) {
		const hovered = event.currentTarget as HTMLElement;
		const sibling = hovered.nextElementSibling; // returns the element immediately following the current one in the parent's children list

		// check for truthy value (sibling exists and nextElementSibling did not return null)
		if (sibling) {
			sibling.classList.toggle("link-hovered");
		}
	}

	onMount(() => {
		let navBar: HTMLElement | null = document.querySelector("nav");

		// function to run on scroll
		function handleScroll() {
			let scrollHeight = window.scrollY;

			if (!navBar) return; // return if navbar is null

			if (scrollHeight > navBar.clientHeight) {
				navBar.classList.add("bg-zinc-950/90");
			} else {
				navBar.classList.remove("bg-zinc-950/90");
			}
		}

		document.addEventListener("scroll", handleScroll);
	});

	// mobile navbar hamburger icon click
	let mobileNavClicked: boolean = $state(false);
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
	<nav class="h-20 flex justify-start md:justify-between gap-4 md:gap-0 sticky top-0 px-10 md:px-40 lg:px-25 xl:px-60 z-100 transition-all duration-500 {mobileNavClicked ? 'bg-zinc-950/90' : ''}">
		<!-- Mobile Nav Hamburger Icon -->
		<div class="flex justify-start self-center md:hidden z-0 text-3xl font-bold">
			<button onclick={() => mobileNavClicked = !mobileNavClicked}>☰</button>
		</div>

		<a href="/" class="md:w-1/2 text-3xl font-bold h-full flex items-center justify-start">KW</a>
		<!-- Desktop Nav -->
		<div class="hidden md:flex w-4xl justify-between items-center z-0">
			<div class="relative">
				<a href="/" class="text-neutral-100 z-20 relative" onmouseenter={handleNavHover} onmouseleave={handleNavHover}>Home</a>
				<div class="link-block z-10"></div>
			</div>

			<div class="relative">
				<a href="#projectsWrapper" class="text-neutral-100 z-20 relative" onmouseenter={handleNavHover} onmouseleave={handleNavHover}>Projects</a>
				<div class="link-block z-10"></div>
			</div>

			<div class="relative">
				<a href="#experienceWrapper" class="text-neutral-100 z-20 relative" onmouseenter={handleNavHover} onmouseleave={handleNavHover}>Experience</a>
				<div class="link-block z-10"></div>
			</div>

			<div class="relative">
				<a href="#educationWrapper" class="text-neutral-100 z-20 relative" onmouseenter={handleNavHover} onmouseleave={handleNavHover}>Education</a>
				<div class="link-block z-10"></div>
			</div>
		</div>
	</nav>

	<!-- Mobile Nav -->
	<div class="grid grid-rows-4 md:hidden px-10 fixed top-20 left-0 right-0 sm:right-1/2 bottom-0 z-100 bg-zinc-950 transition-transform duration-250 {mobileNavClicked ? 'translate-x-0' : '-translate-x-1/1'}" id="mobileNav">
		<div class="relative my-auto">
			<a href="/" class="text-neutral-100 z-20 relative" onclick={() => mobileNavClicked = false}>Home</a>
		</div>

		<div class="relative my-auto">
			<a href="#projectsWrapper" class="text-neutral-100 z-20 relative" onclick={() => mobileNavClicked = false}>Projects</a>
		</div>

		<div class="relative my-auto">
			<a href="#experienceWrapper" class="text-neutral-100 z-20 relative" onclick={() => mobileNavClicked = false}>Experience</a>
		</div>

		<div class="relative my-auto">
			<a href="#educationWrapper" class="text-neutral-100 z-20 relative" onclick={() => mobileNavClicked = false}>Education</a>
		</div>
	</div>

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