<script lang="ts">
	import pfp from '$lib/assets/pfp.jpg';
	import { onMount } from 'svelte';

	function getCenterOfElement(el: HTMLElement) {
		const boundingBox = el.getBoundingClientRect();
		const centerX = boundingBox.left + boundingBox.width / 2;
		const centerY = boundingBox.top + boundingBox.height / 2;
		return {x: centerX, y: centerY};
	}

	let mainContainer: HTMLElement;
	const PARALLAX_AMOUNT = 35; // Higher is less movement

	onMount(() => {
		function handleMouseMovement(event: MouseEvent) {
			const mouseX = event.clientX;
			const mouseY = event.clientY;
			const centerCoords = getCenterOfElement(mainContainer);

			mainContainer.style.transform = `translate(${(centerCoords.x - mouseX) / PARALLAX_AMOUNT}px, ${(centerCoords.y - mouseY) / PARALLAX_AMOUNT}px)`;

		}

		document.addEventListener("mousemove", handleMouseMovement);

		return () => {
			document.removeEventListener("mousemove", handleMouseMovement);
		};
	});

</script>

<div id="heroContent" bind:this={mainContainer} class="flex justify-center items-center gap-5 mx-auto pt-80">
	<div class="min-w-0 flex justify-end">
		<!-- Image goes here	-->
		<img class="w-sm" src={pfp} alt="Korben" />
	</div>
	<div class="">
		<h1 class="text-5xl">Hi, my <br/> name is <span><b>Korben.</b></span></h1>
		<h2 class="text-4xl">A software developer from <br /><b>New Jersey.</b></h2>
	</div>
</div>
