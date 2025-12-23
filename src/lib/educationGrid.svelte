<script lang="ts">
import Education from './educationIndividual.svelte';
</script>

<div class="flex flex-col lg:grid lg:grid-cols-1 px-10 md:px-40 lg:px-25 xl:px-60 gap-4 h-full">
	<h1 class="text-5xl font-bold mb-6">Education</h1>

	<Education major="B.S. in Software Development" school="Grand Canyon University (Expected Spring 2027)" coursework={['C#', 'Java', 'Python', 'SQL', 'MongoDB', 'ASP.NET', 'Spring Boot']} start="Autumn 2024" end="Present">
		Minor in Machine Learning. <br>
		Research Intern for Canyon AI Research. <br>
		Software developer for the AIM Navigator project - a Canyon AI Research project.
	</Education>

	<Education major="Computer Science Coursework" school="William Paterson University of New Jersey" coursework={['C++']} start="Spring 2024">
		<b>Transferred to Grand Canyon University prior to completion of degree.</b> <br/>
		Student Government Association Senate member.
	</Education>

	<Education major="Computer Science Coursework" school="Raritan Valley Community College" coursework={['HTML', 'CSS', 'JavaScript', 'Unity', 'C#']} start="Autumn 2023" end="Spring 2024">
		<b>Transferred to William Paterson University of New Jersey prior to completion of degree.</b>
	</Education>
</div>