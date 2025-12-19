<script lang="ts">
import Experience from './experienceIndividual.svelte';
</script>

<div class="flex flex-col lg:grid lg:grid-cols-1 px-10 md:px-40 lg:px-25 xl:px-60 gap-4 h-full">
	<h1 class="text-5xl font-bold mb-6">Experience</h1>

	<Experience title="Events A/V Student Worker" company="Grand Canyon University" skills={['Dante']} start=" August 2025" end="Present">
		<p>Set up and struck audio and lighting systems for GCU Arena events, including chapels, concerts, and athletics.
			Mixed live audio, managed SMIs, and coordinated with event staff to ensure smooth A/V operations.
			Spotlight operation for NCAA Division I athletic events</p>
	</Experience>

	<Experience title="Contract Audio Engineer" company="Cornerstone Church" skills={['Dante', 'Audio Mixing', 'Midas M32', 'Waves SoundGrid']} start="March 2025" end="Present">
		<p>Set up and struck audio and lighting systems for GCU Arena events, including chapels, concerts, and athletics. Mixed live audio, managed SMIs, and coordinated with event staff to ensure smooth A/V operations. Spotlight operation for NCAA Division I athletic events</p>
	</Experience>

	<Experience title="AVL Tech" company="Hume Lake Christian Camps" skills={['Dante', 'Audio Mixing', 'Allen & Heath Avantis', 'QLab Programming']} start=" May 2025" end="August 2025">
		<p>Mixed live audio for daily skits and presentations, edited recordings, configured wireless audio gear. Troubleshot MIDI, QLab, ProPresenter, and Chroma-Q Vista systems, and managed Dante audio devices for seamless performances.</p>
	</Experience>

	<Experience title="Production Sound Tech" company="Hume Lake Christian Camps" skills={['Dante', 'Audio Mixing', 'Roland M5000']} start=" May 2024" end="August 2024">
		<p>Mixed live audio for daily skits and sermons, configured wireless audio and networking gear. Communicated with the camp director to ensure audio requirements for the camp are fulfilled</p>
	</Experience>
</div>