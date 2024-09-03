<script lang="ts">
	import { base } from '$app/paths';
	export let name: string;
	export let date: string;
	export let src: string;
</script>

<div class="flex border-2 border-primary-500 p-2 w-80 md:w-96 items-center">
	<img class="max-w-32 mr-4" src={src} alt='Next event'>
	<div class='flex-grow'>
		<div class="flex flex-col gap-2">
			<h3 class="h3 text-primary-500">Próximamente</h3>
			<div>
				<h4 class="h4">{name}</h4>
				<p>{date}</p>
			</div>
		</div>
	</div>
</div>