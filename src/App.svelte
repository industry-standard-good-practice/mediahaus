<script>
	import Card from './components/Card.svelte';
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	const contents = [
		{
			user: {
				username: 'Noah Semus',
				profilePic:
					'https://images.pexels.com/photos/3222422/pexels-photo-3222422.jpeg?auto=compress&cs=tinysrgb&h=650&w=940',
			},
			userReview: {
				title: 'Pulp Fiction',
				rating: '8.5/10',
				review: 'Bloody and gory. Fun time.',
				poster: 'http://cdn.shopify.com/s/files/1/0969/9128/products/Pulp_Fiction_-_Uma_Thurman_Mia_Wallace_-_Quentin_Tarantino_Hollywood_Movie_Poster_b9d2e54b-a73e-46fc-8435-fcc672c41424_grande.jpg?v=1572088239',
			},
		},
		{
			user: {
				username: 'Jack Trego',
				profilePic:
					'https://images.pexels.com/photos/6507483/pexels-photo-6507483.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260',
			},
			userReview: {
				title: 'The Silence of the Lambs',
				rating: '9/10',
				review: 'Intriguing. Classic polic procedural. Good.',
				poster: 'https://m.media-amazon.com/images/M/MV5BNjNhZTk0ZmEtNjJhMi00YzFlLWE1MmEtYzM1M2ZmMGMwMTU4XkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_.jpg',
			},
		},
		{
			user: {
				username: 'Jack Trego',
				profilePic:
					'https://images.pexels.com/photos/6507483/pexels-photo-6507483.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260',
			},
			userReview: {
				title: 'The Silence of the Lambs',
				rating: '9/10',
				review: 'Intriguing. Classic polic procedural. Good.',
				poster: 'https://m.media-amazon.com/images/M/MV5BNjNhZTk0ZmEtNjJhMi00YzFlLWE1MmEtYzM1M2ZmMGMwMTU4XkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_.jpg',
			},
		},
	];

	let ready = false;
	onMount(() => (ready = true));
</script>

<main>
	<div class="topBar" />
	<div class="container">
		{#if ready}
			{#each contents as content, i}
				<div transition:fly={{ y: 80, duration: 1000, delay: i * 200 }}>
					<Card {...content} />
				</div>
			{/each}
		{/if}
	</div>
</main>

<style>
	main {
		background: var(--sys--dark--background);
		width: 100vw;
		height: 100vh;
		overflow-y: auto;
		overflow-x: hidden;
	}

	.container {
		display: flex;
		flex-direction: column;
		gap: 16px;
		padding: 16px;
		overflow: hidden;
		margin-top: 80px;
	}

	.topBar {
		width: 100vw;
		height: 80px;
		background: black;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 9;
	}
</style>
