<script>
	import photo from '../lib/images/logo.png'
	import photo1 from '../lib/images/1.jpg'
	import photo2 from '../lib/images/2.png'
	import photo5 from '../lib/images/5.jpg'
	import photo6 from '../lib/images/6.jpg'
	import Navbar from '../components/Navbar.svelte'

	export let r = 0;
	const photos = [photo6, photo1, photo2, photo5];
	const texts = ["Studyo Murekkep", "Ilay ve Mert", "", "Penna Band"];
	let keycount = r;

	function keyemoji() {
		if (keycount == 3) {
			keycount = 0;
		} else {
			keycount = keycount + 1;
		}
	}
	setInterval(() => {
		keyemoji();
	}, 5000);



</script>

<svelte:head>
	<title>penna.band</title>
	<meta name="description" content="Svelte demo app" />
	{#each photos as image}
    	<link rel="preload" as="image" href={image} />
  	{/each}
</svelte:head>

<div class="py-10 space-y-10">
	<div class="md:-space-y-[8vh] -space-y-[5vh] w-full">
		<Navbar />
		<div class=" grid justify-items-center group">
			{#key photos[keycount]}
				<img src={photos[keycount]} class="md:w-1/2 w-3/4 bw z-0 md:group-hover:w-3/4 group-hover:w-full  md:h-[50vh] h-[50vh] object-cover fadein transition-all" alt="">
				<p class="md:w-1/2 w-3/4 yg fadein md:text-md text-xs md:group-hover:w-3/4 group-hover:w-full transition-all">{texts[keycount]}</p>

			{/key}
		</div>
	</div>
</div>

<style>

	.yg{
		font-family: 'Young Serif', serif;
		color: rgb(90, 90, 90);
	}

	.bw {
		-webkit-filter: grayscale(100%); /* Safari 6.0 - 9.0 */
		filter: grayscale(100%);
	}

	.fadein {
		animation: fadein 1s;
		-webkit-animation: fadein 1s;
		-moz-animation: fadein 1s;
		-o-animation: fadein 1s;
		-ms-animation: fadein 1s;
	}

	@keyframes fadein {
		from {
			opacity: 0;
		}

		to {
			opacity: 1;
		}
	}
</style>