<script lang="ts">
import Experience from './experienceIndividual.svelte';
</script>

<div class="flex flex-col lg:grid lg:grid-cols-1 px-10 md:px-40 lg:px-25 xl:px-60 gap-4 h-full">
	<h1 class="text-5xl font-bold mb-6">Experience</h1>

	<Experience title="AI-Assisted Developer Intern" company="TownBackyard" skills={['ASP.NET', 'HTML/CSS', 'SASS', 'Git', 'Agentic AI Development']} start="May 2026" end="Present">
		<p>Redesigned the front end of townbackyard.com (ASP.NET), including an in-progress migration of the site’s styling
			from CSS to SASS for improved maintainability.
			Evaluated AI coding agents (Claude Code, OpenAI Codex) against traditional workflows to guide their use on the
			redesign.</p>
	</Experience>

	<Experience title="A/V Student Technician" company="Grand Canyon University" skills={['Dante', 'Audio Mixing']} start="August 2025" end="Present">
		<p>Set up and struck audio, lighting, and video systems for university events, ensuring smooth on-site operation.
			Trained incoming staff ahead of the 2026 school year</p>
	</Experience>

	<Experience title="AVL Tech" company="Hume Lake Christian Camps" skills={['Dante', 'Audio Mixing', 'Show Control Programming', 'Team Management']} start=" May 2026" end="August 2026">
		<p>Mixed live audio and operated QLab, ProPresenter, Chroma-Q Vista, and Dante networked devices for daily chapel
			programs.
			Programmed a custom show-control automation setup using the Bitfocus Companion platform.
			Led the production team for the middle school camp, coordinating directly with camp directors to meet technical
			requirements.</p>
	</Experience>
</div>