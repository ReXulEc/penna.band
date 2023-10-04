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
		<!-- svelte-ignore a11y-invalid-attribute -->
		<a href="#" role="button" on:click={keyemoji} class="grid justify-items-center group">

			{#key photos[keycount]}
				<img src={photos[keycount]} class="md:w-1/2 w-5/6 bw z-0 md:group-hover:w-3/4 group-hover:w-full md:h-[50vh] h-[50vh] object-cover fadein transition-all" alt="">
				<p class="md:w-1/2 w-5/6 volkorn fadein md:text-md text-xs md:group-hover:w-3/4 group-hover:w-full transition-all">{texts[keycount]}</p>
			{/key}
		</a>
	</div>
	<div class="grid justify-items-center">
		<div class="md:w-1/2 w-5/6 volkorn space-y-2">
			<p>Penna olarak, müziğin ve yaşamın karmaşıklığını yakalayan bir müzik grubuyuz. 2023 yılının başlarında, İzmir'in gölgeleri içinde kurulduk. Metal ve punk türlerini birleştirerek kendi benzersiz müziğimizi yaratmaya çalışıyoruz.</p>
			<p>Kuruluşumuzdan bu yana, İzmir'in karmaşık ve çoğu zaman unutulmuş sokaklarında çalışıyoruz. Dört üyemiz - Mert ve Sezer elektro gitarlarda, Taha bateride ve Ilay vokalde - müziğin derinliklerine dalmak için her zaman bir arayış içinde. Şarkılarımızda, hayatın iniş çıkışlarına ve insan deneyimine duyduğumuz hayranlık ve saygıyı yansıtmaya çalışıyoruz.</p>
			<p>Müziğimiz, sertlik ve karanlıkla tanımlanıyor. Melankoli ve çaresizlik, şarkılarımızın temel taşlarından biri haline geldi. Hayatın acımasız gerçekleri, sözlerimize ve melodilere damgasını vuruyor. İfade etmek istediğimiz hisler, genellikle dünya ile barışık bir şekilde yaşayamadığımızı gösteriyor. Bazen de tam tersini.</p>
			<p>Sahne ışıkları altında henüz büyük bir tanıtıma sahip olmayabiliriz, ancak sahnede olma arzusu ve yeteneğimiz var. Performanslarımızı paylaşmak, duygularımızı daha geniş bir kitleye iletmek için önemli bir adım olacak. Şu an elimizde resmi bir kayıt olmasa da, bir cover albümü üzerinde çalışıyoruz ve kendi orijinal şarkılarımızı oluşturmak için ilham almaya devam ediyoruz.</p>
			<p>Sosyal medyada <a class="text-white font-bold" href="https://instagram.com/pennaband">@pennaband</a> hesabımızı takip ederek, müziğimize ve yolculuğumuza katılabilirsiniz. Belki de bir gün, müziğimizin renkleri sizinle daha fazla insanı aydınlatır ve bu dünyada bir fark yaratabiliriz. Umutsuzluktan çok, müziğin gücünün ve insan bağlarının farkında olan bir grup olarak, gelecekteki yeni müzikal serüvenlere hazırız.</p>
		</div>
	</div>
</div>

<style>

	.yg{
		font-family: 'Young Serif', serif;
		color: rgb(90, 90, 90);
	}
	
    .volkorn {
		font-family: 'Vollkorn', serif;
		color: rgb(167, 167, 167);

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