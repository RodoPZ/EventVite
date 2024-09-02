<script lang="ts">
	import Menu from '$lib/components/Menu.svelte';
	import '../app.postcss';

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup, initializeStores, Modal } from '@skeletonlabs/skeleton';
	initializeStores();

	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>

<div class="grid grid-rows-[auto_1fr_auto] h-screen w-screen">
	<!-- Header -->
	<header class="bg-red-500">
		<Menu />
	</header>
	<!-- Page -->
	<div class="w-full flex items-center justify-center">
		<div class="p-5 max-w-7xl w-full">
			<slot />
		</div>
	</div>

	<Modal />
</div>


