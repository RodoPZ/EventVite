<script lang="ts">
	import { Drawer, getDrawerStore } from '@skeletonlabs/skeleton';
	import { AppBar } from '@skeletonlabs/skeleton';
	import MaterialSymbolsMenu from '~icons/material-symbols/menu';	
	import MaterialSymbolsClose from '~icons/material-symbols/close';
	import { page } from '$app/stores';
	import LogosWhatsappIcon from '~icons/logos/whatsapp-icon';
	import { base } from '$app/paths';

	const drawerStore = getDrawerStore();
	
	function handleOpen() {
		drawerStore.open();
	}
	function handleClose() {
		drawerStore.close();
	}
	$: classesActive = (href: string) => (`${base}${href}` === $page.url.pathname ? '!variant-filled-primary' : '');
</script>

<div>
	<Drawer >
		<div class="m-4">
			<button type="button" class="btn-icon btn-icon-sm bg-initial" on:click={handleClose}>
				<MaterialSymbolsClose style="font-size: 1.2rem"/>
			</button>
		</div>
		<nav class="list-nav p-4">
			<ul>
				<li>
					<a href="{base}/events/noche-muy-mexicana" class="{classesActive("/events/noche-muy-mexicana")}" on:click={handleClose}>
						<h5 class="h5 w-full text-center">🤠 Una Noche Muy Mexicana 🎉</h5>
					</a>
				</li>
				<li>
					<a href="{base}/events" class="{classesActive("/events")}" on:click={handleClose}>
						<h5 class="h5 w-full text-center">Más eventos</h5>
					</a>
				</li>
				<li>
					<a href="{base}/events/noche-muy-mexicana/media" class="{classesActive("/events/noche-muy-mexicana/media")}" on:click={handleClose}>
						<h5 class="h5 w-full text-center">Fotos</h5>
					</a>
				</li>
			</ul>
		</nav>
	</Drawer>
	<AppBar slotDefault="place-self-center" slotTrail="place-content-end">
		<!-- <svelte:fragment slot="lead"> 
			<button type="button" class="btn-icon btn-icon-sm bg-initial md:hidden" on:click={handleOpen}>
				<MaterialSymbolsMenu style="font-size: 1.2rem"/>
			</button>
		</svelte:fragment> -->
		<svelte:fragment slot="trail">
			<a class="btn hover:variant-soft-primary flex flex-row items-center justify-center gap-4" href="https://chat.whatsapp.com/EA7jHlJYkTPJOo6FRej0BS">
				<h4 class="h4">Comprar boletos</h4>
				<LogosWhatsappIcon/>
			</a>
		</svelte:fragment>
	</AppBar>
</div>
