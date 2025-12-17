<script lang="ts">
	// import pfp image
	import pfp from '$lib/assets/pfp.jpg';
	import { onMount } from 'svelte';

	// helper function to get the center of an HTMLElement
	function getCenterOfElement(el: HTMLElement) {
		const boundingBox = el.getBoundingClientRect();
		const centerX = boundingBox.left + boundingBox.width / 2;
		const centerY = boundingBox.top + boundingBox.height / 2;
		return {x: centerX, y: centerY};
	}

	let mainContainer: HTMLDivElement; // empty variable of HTMLDivElement type that will be assigned a reference using bind:this on the element itself
	const PARALLAX_AMOUNT = 35; // Higher is less movement

	// onMount is a lifecycle hook that schedules a callback function to run as soon as the component (this file in this case) is inserted (mounted) to the DOM.
	// () => {} is the callback declaration
	onMount(() => {
		// local function that is scoped to this particular component
		function handleMouseMovement(event: MouseEvent) {
			const mouseX = event.clientX;
			const mouseY = event.clientY;
			const centerCoords = getCenterOfElement(mainContainer);

			mainContainer.style.transform = `translate(${(centerCoords.x - mouseX) / PARALLAX_AMOUNT}px, ${(centerCoords.y - mouseY) / PARALLAX_AMOUNT}px)`;

		}

		// attaches the handleMouseMovement function to the mousemove event.
		// handleMouseMovement will be called everytime the mousemove event is triggered.
		document.addEventListener("mousemove", handleMouseMovement);

		// return a callback/cleanup function.
		// this is run when this component is destroyed/unmounted.
		// not returning a cleanup function would result in the event listener sticking around after the component is destroyed
		return () => {
			document.removeEventListener("mousemove", handleMouseMovement);
		};
	});

	// import tsparticles
	import { tsParticles } from '@tsparticles/engine';
	import { loadStarsPreset } from '@tsparticles/preset-stars';

	// this is called an Immediately Invoked Function Expression (IIFE)
	// surrounding the function in parentheses ( ... ) turns it into a function expression
	// and adding (); to the end invokes the function immediately
	(async () => {
		await loadStarsPreset(tsParticles);
	})();

	// run the tsParticles.load function when this component is mounted
	// this attaches tsParticles to the tsParticles div
	onMount(() => {

		let options = {
			preset: "stars", // loads the stars preset
			background: {
				opacity: 0 // makes the background transparent
			}
		}

		tsParticles.load({
			id: "tsParticles",
			options: options
		});
	});

</script>

<style>
	#heroContent {
			transition: transform 0.5s ease-out;
	}
</style>

<!-- bind:this sets a reference of this DOM element (heroContent div) to the provided variable (mainContainer)-->
<div id="heroContent" bind:this={mainContainer} class="flex justify-center items-center gap-5 mx-auto pt-50 relative z-10">
	<div class="min-w-0 flex justify-end">
		<!-- Image goes here	-->
		<img class="w-sm" src={pfp} alt="Korben" />
	</div>
	<div class="">
		<h1 class="text-5xl">Hi, my <br/> name is <span><b>Korben.</b></span></h1>
		<h2 class="text-4xl">A software developer from <br /><b>New Jersey.</b></h2>
	</div>
</div>

<div id="tsParticles" class="w-full h-screen absolute top-0"></div>
