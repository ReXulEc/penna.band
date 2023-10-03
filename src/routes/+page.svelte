<script>
	import photo from '../lib/images/logo.png'
	import photo1 from '../lib/images/1.jpg'
	import photo2 from '../lib/images/2.png'
	import photo3 from '../lib/images/3.png'
	import photo4 from '../lib/images/4.png'
	import photo5 from '../lib/images/5.jpg'
	import photo6 from '../lib/images/6.jpg'



</script>

<svelte:head>
	<title>penna.band</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<div class="py-10 space-y-10">
	<div class="md:-space-y-[8vh] -space-y-[5vh] w-full">
		<div class=" flex justify-center">
			<img src={photo} class="md:w-2/12 w-4/12 z-20" alt="">
		</div>
		<div class=" grid justify-items-center">
			<img src={photo6} class="md:w-1/2 w-3/4 bw z-0  md:h-[50vh] h-[50vh]  object-cover" alt="">
		</div>
	</div>
	<div class="h-[1px] w-full bg-[#111111]">

	</div>
</div>

<style>
	.bw {
		-webkit-filter: grayscale(100%); /* Safari 6.0 - 9.0 */
		filter: grayscale(100%);
	}
</style>