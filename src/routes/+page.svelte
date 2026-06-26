<script lang="ts">
	import yay from '$lib/assets/yay.gif';

	let playing = $state(false);
</script>

<svelte:head>
	<title>jolly</title>
	<meta
		name="description"
		content="Ship something jolly, get Jolly Ranchers shipped to your door. A Hack Club YSWS event."
	/>
	<link
		href="https://fonts.googleapis.com/css2?family=Architects+Daughter&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<main class="flex min-h-screen flex-col items-center px-4 py-12 gap-8 text-2xl text-center">
	<marquee><b>!!! SHIP NOW SHIP NOW SHIP NOW !!! </b></marquee>

	<h1 class="text-7xl font-extrabold text-[red]">J O L L Y</h1>

	<div class="flex flex-row gap-2">
		<img src={yay} />
		<img src={yay} />
		<img src={yay} />
		<img src={yay} />
		<img src={yay} />
	</div>

	<p>ys: a jolly project (joyous? christmasty? any way you interpret it!) for 3+ hours</p>

	<p>
		ws: jolly ranchers + a postcard signed by <a
			href="https://hackclub.enterprise.slack.com/team/U08CJCZ2Z9S"
			class="text-[blue] underline decoration-2 font-bold"
			target="_blank">Jolly</a
		> from hq!
	</p>

	<div class="flex flex-row gap-2">
		<img src={yay} />
		<img src={yay} />
		<img src={yay} />
		<img src={yay} />
		<img src={yay} />
	</div>

	<div>
		<a
			href="https://forms.hackclub.com/jolly-submit"
			class="text-5xl font-semibold text-[blue] underline decoration-[4px]"
			>MORE INFO &amp; SUBMIT!!</a
		>
	</div>

	<div class={['flex flex-wrap gap-6 items-center', playing && 'flex-col']}>
		<a
			target="_blank"
			href="https://hackclub.enterprise.slack.com/"
			class="text-[blue] underline decoration-2 cursor-pointer">slack</a
		>

		{#if playing}
			<iframe
				src="https://www.youtube.com/embed/ig-78RVSLVs?start=91&autoplay=1&playsinline=1"
				title="AJR - Christmas in June (Official Video)"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
				referrerpolicy="strict-origin-when-cross-origin"
				allowfullscreen
				class="max-w-[95vw] max-h-[70vh] w-[800px] h-[600px]"
			></iframe>
		{:else}
			<a class="text-[blue] underline decoration-2 cursor-pointer" onclick={() => (playing = true)}
				>play</a
			>
		{/if}
	</div>
</main>

<style>
	:global(html) {
		background: url('$lib/assets/jolly.png') repeat;
		background-size: 20vw auto;
	}

	main {
		font-family: 'Architects Daughter', 'Comic Sans MS', sans-serif;
	}
</style>
