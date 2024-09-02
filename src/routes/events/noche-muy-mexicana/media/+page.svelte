<script lang="ts">
	import { getModalStore, type ModalSettings } from '@skeletonlabs/skeleton';
			
	const modalStore = getModalStore();
	const ImageSrc = "https://images.unsplash.com/photo-1617296538902-887900d9b592?ixid=M3w0Njc5ODF8MHwxfGFsbHx8fHx8fHx8fDE2ODc5NzExMDB8&ixlib=rb-4.0.3";

	function onClose() {
		modalStore.close();
	}

	const modal: ModalSettings = {
		type: 'alert',
		// Data
		title: 'Example Alert',
		body: 'This is an example modal.',
		image: 'https://i.imgur.com/WOgTG96.gif',
	};

	function onOpen() {
		modalStore.trigger(modal);
	}
</script>

<div class="flex flex-col gap-2 h-min-screen">
	<h1 class="h1">Evento actual</h1>

	<section class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-2">
		{#each Array(6) as _, i}
			<div class="grid gap-4">
				{#each Array(3) as _, i}
					<button type="button" on:click={onOpen}>
						<img class="h-auto max-w-full rounded-lg" src={ImageSrc} alt=""/>
					</button>
				{/each}
			</div>	
		{/each}
	</section>	
</div>

{#if $modalStore[0]}
	<!-- Button -->
	<button class="btn-icon variant-filled fixed top-4 right-4 z-50 font-bold shadow-xl" on:click={onClose}>×</button>
	<!-- Image -->
	<img src={ImageSrc} class={"max-w-[90%] max-h-[90%] rounded-container-token overflow-hidden shadow-xl"} alt="Example" />
{/if}