<script>
	import CountDownClock from "$lib/components/CountDownClock.svelte";
	import InfoChip from "$lib/components/InfoChip.svelte";
	import InfoGrid from "$lib/components/InfoGrid.svelte";
	import LogosWhatsappIcon from '~icons/logos/whatsapp-icon';
	import MdiExternalLink from '~icons/mdi/external-link';

	let dataForGrid = [
        {
            title: "Ubicación",
            content: `
				<a class="anchor" href="https://maps.app.goo.gl/fVcPAzMWTQhPiZBs5">
					<h4 class="h4">Red Garden 🔗</h4>
				</a>
			`
        },
        {
            title: "Día",
            content: "13 de Septiembre"
        },
		{
            title: "Hora",
            content: "09:00 PM"
        },
        {
            title: "Costos",
            content: [
                '<p class="line-through text-surface-500 ">Fase 1: $60</p>',
                "Fase 2: $80",
                "Día del evento: $100"
            ]
        }
    ];

	let dataForChips = [
		{
			title: "Detalles",
			content: "<p class='text-justify'>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quis accusantium accusamus fuga rerum consectetur placeat, cum hic rem, quos excepturi quo, architecto error tenetur eos! Saepe dolor ea mollitia ipsa fuga quia iusto, deleniti deserunt laborum nostrum. Laudantium sed, sunt, architecto magni ipsum, neque autem tenetur inventore fuga porro provident!</p>"
		},
		{
			title: "Reglas",
			content: "<ul><li>Prohibido el acceso a menores de edad</li></ul>"
		},
		{
			title: "Fotos",
			content: "<a class='anchor' href='/'> Al final del evento publicaremos las fotos</a>"
		},
		{
			title: "Proximamente",
			content: `
				<div class='w-full flex justify-center items-center'>
					<img style='width: 100px' src='https://www.nomadfoods.com/wp-content/uploads/2018/08/placeholder-1-e1533569576673-960x960.png' alt='Next event'>
					<div class="flex flex-col gap-2 ml-4">
						<h4>Spookypeda</h4>
						<p>13 de Septiembre</p>
					</div>
				</div>
			`		
		}
	];
</script>

<div>
	<div class="md:grid md:grid-cols-2 gap-8">
		<img class="md:hidden" src="/images/una_fiesta_muy_mexicana_baner.jpg" alt="event banner">
		<div class="flex flex-col md:items-center md:justify-center">
			<h1 class="h2 py-5 text-center">Noche Muy Mexicana</h1>
			<CountDownClock/>
			<hr class="w-full !border-t-2 my-4">
			<InfoGrid data={dataForGrid}/>
			<hr class="w-full !border-t-2 my-4">
			<a class="anchor flex flex-row items-center justify-center gap-4" href="/events/1/media">
				<h2 class="h2">Comprar boletos</h2>
				<LogosWhatsappIcon/>
			</a>
		</div>
		<img class="hidden md:block md:grid-ri max-w-[604px]" alt="event banner">
	</div>

	<div class="flex w-full h-full flex-col items-center justify-center p-2 gap-3">

		<hr class="w-full !border-t-2 my-4">
		{#each dataForChips as data}
			<InfoChip title={data.title} content={data.content}/>
		{/each}
	</div>
</div>

