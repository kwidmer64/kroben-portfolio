<script lang="ts">
	import { page } from '$app/state';
</script>

<div class="flex flex-col items-center mt-25 gap-5">
	<h1 class="text-5xl font-bold">Something went wrong!</h1>
<p class="text-3xl font-semibold">{page.status} - {page.error?.message}</p> <!-- ? used to if error is null -->
</div>