<script>
	import Card from '../components/Card.svelte';
	import TopBar from '../components/TopBar.svelte';
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	let contents = [
		{
			user: {
				username: 'Noah Semus',
				profilePic:
					'https://images.pexels.com/photos/3222422/pexels-photo-3222422.jpeg?auto=compress&cs=tinysrgb&h=650&w=940'
			},
			userReview: {
				title: 'Pulp Fiction',
				rating: '8.5',
				review: 'Bloody and gory. Fun peter.',
				poster:
					'http://cdn.shopify.com/s/files/1/0969/9128/products/Pulp_Fiction_-_Uma_Thurman_Mia_Wallace_-_Quentin_Tarantino_Hollywood_Movie_Poster_b9d2e54b-a73e-46fc-8435-fcc672c41424_grande.jpg?v=1572088239'
			}
		},
		{
			user: {
				username: 'Jack Trego',
				profilePic:
					'https://images.pexels.com/photos/6507483/pexels-photo-6507483.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260'
			},
			userReview: {
				title: 'The Silence of the Lambs',
				rating: '9',
				review: 'Intriguing. Classic police procedural. Good.',
				poster:
					'https://m.media-amazon.com/images/M/MV5BNjNhZTk0ZmEtNjJhMi00YzFlLWE1MmEtYzM1M2ZmMGMwMTU4XkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_.jpg'
			}
		},
		{
			user: {
				username: 'Jack Trego',
				profilePic:
					'https://images.pexels.com/photos/6507483/pexels-photo-6507483.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260'
			},
			userReview: {
				title: 'The Silence of the Lambs',
				rating: '9',
				review: 'Intriguing. Classic police procedural. Good.',
				poster:
					'https://m.media-amazon.com/images/M/MV5BNjNhZTk0ZmEtNjJhMi00YzFlLWE1MmEtYzM1M2ZmMGMwMTU4XkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_.jpg'
			}
		}
	];

	let ready = false;
	onMount(() => (ready = true));
</script>

<main>
	<TopBar />
	<div class="container">
		{#key ready}
			{#each contents as content, i}
				<div
					in:fly={{
						y: 80,
						duration: 1000,
						delay: 200 * i
					}}
				>
					<Card {...content} />
				</div>
			{/each}
		{/key}
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
		margin-top: 70px;
	}
</style>
