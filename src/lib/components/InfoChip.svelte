<script>
	export let title;
	export let content;
</script>

<div class="w-full flex flex-col gap-2 mt-2">
	<h4 class="h4">{title}</h4>
	<div class="ml-5">
		{@html content}
	</div>
</div>