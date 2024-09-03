<script>
	import CountDownClock from "$lib/components/CountDownClock.svelte";
	import InfoChip from "$lib/components/InfoChip.svelte";
	import InfoGrid from "$lib/components/InfoGrid.svelte";
	import LogosWhatsappIcon from '~icons/logos/whatsapp-icon';
	import MdiExternalLink from '~icons/mdi/external-link';
	import { base } from '$app/paths';
	import NextParty from "$lib/components/NextParty.svelte";


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
			title: "Temática",
			content: "Mexicanos"
		},
        {
            title: "Costos",
            content: [
                '<p class="text-surface-400 line-through">Fase 1: $60</p>',
                '<p >Fase 2: $80</p>',
                '<p class="text-surface-400 line-through">Día del evento: $100</p>'
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
			content: "<p> Al final del evento publicaremos las fotos</p>"
		}
	];
</script>

<div>
	<div class="md:grid md:grid-cols-2 gap-8">
		<img class="md:hidden" src="{base}/images/una_fiesta_muy_mexicana_baner.jpg" alt="event banner">
		<div class="flex flex-col md:items-center md:justify-center gap-4">
			<h1 class="h1 py-5 text-center">Noche Muy Mexicana</h1>
			<div class="flex justify-center">
				<CountDownClock/>
			</div>
			<hr class="w-full !border-t-2 my-4">
			<InfoGrid data={dataForGrid}/>
			<hr class="w-full !border-t-2 my-4">
			<a class="anchor flex flex-row items-center justify-center gap-4" href="https://chat.whatsapp.com/EA7jHlJYkTPJOo6FRej0BS">
				<h2 class="h2">Comprar boletos</h2>
				<LogosWhatsappIcon/>
			</a>
		</div>
		<div class="hidden md:flex md:justify-center md:items-center">
			<img class="md:block w-full max-w-[500px] h-[600px] bg-surface-400 object-cover object-top" 
				src="{base}/images/una_fiesta_muy_mexicana_baner.jpg"  
				alt="event banner"
			>
		</div>
	</div>

	<div class="flex w-full h-full flex-col items-center justify-center p-2 gap-3">

		<hr class="w-full !border-t-2 my-4">
		{#each dataForChips as data}
			<InfoChip title={data.title} content={data.content}/>
		{/each}
	</div>
	<div class="flex flex-col md:flex-row justify-center w-full mt-3 gap-4">
		<NextParty name="Spookypeda Vol.3" date="25 de Octubre" src="{base}/images/spookypeda_banner.jpg"/>
		<NextParty name="Post Halloween Party Vol.3" date="1 de Noviembre" src="{base}/images/posthalloween_banner.jpg"/>
	</div>
</div>

