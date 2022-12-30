<script>
	import ForYouCard from '../components/ForYouCard.svelte';
	import FriendCard from '../components/FriendCard.svelte';
	import TopBar from '../components/TopBar.svelte';

	let posts = [
		{
			user: {
				username: 'Noah Semus',
				profilePic:
					'https://images.pexels.com/photos/3222422/pexels-photo-3222422.jpeg?auto=compress&cs=tinysrgb&h=650&w=940'
			},
			userReview: {
				title: 'Pulp Fiction',
				rating: '8.5',
				review: 'A bloody, gory, fun masterpiece.',
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
</script>

<TopBar />
<div class="feed">
	<section>
		<h1>For You</h1>
		<div class="carousel">
			<ForYouCard />
			<ForYouCard />
			<ForYouCard />
		</div>
	</section>
	<section>
		<h1>Popular Right Now</h1>
		<div class="carousel">
			<a href="somewhere" class="movie-poster">
				<img
					src="https://m.media-amazon.com/images/I/71uKM+LdgFL._AC_UF894,1000_QL80_.jpg"
					alt="Poster of Inception"
				/>
			</a>
			<a href="somewhere" class="movie-poster">
				<img
					src="https://m.media-amazon.com/images/I/71uKM+LdgFL._AC_UF894,1000_QL80_.jpg"
					alt="Poster of Inception"
				/>
			</a>
			<a href="somewhere" class="movie-poster">
				<img
					src="https://m.media-amazon.com/images/I/71uKM+LdgFL._AC_UF894,1000_QL80_.jpg"
					alt="Poster of Inception"
				/>
			</a>
			<a href="somewhere" class="movie-poster">
				<img
					src="https://m.media-amazon.com/images/I/71uKM+LdgFL._AC_UF894,1000_QL80_.jpg"
					alt="Poster of Inception"
				/>
			</a>
			<a href="somewhere" class="movie-poster">
				<img
					src="https://m.media-amazon.com/images/I/71uKM+LdgFL._AC_UF894,1000_QL80_.jpg"
					alt="Poster of Inception"
				/>
			</a>
		</div>
	</section>
	<section>
		<h1>Friends</h1>
		{#each posts as post}
			<FriendCard {...post} />
		{/each}
	</section>
</div>

<style lang="sass">

	// General Styling

	@import url('https://fonts.googleapis.com/css2?family=Public+Sans&display=swap')
	@import url('https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@100,400;125,603&display=swap')

	:global(*)
		margin: 0
		padding: 0
		box-sizing: border-box
		-webkit-tap-highlight-color:  rgba(255, 255, 255, 0)

	:global(::-webkit-scrollbar)
		display: none

	:global(html)
		--primary: #FFAAF2
		--background: #1F1A1D
		--on-background: #EAE0E4
		--surface-1: #31262E

	:global(body)
		background: var(--background)
		color: var(--on-background)
		font-family: 'Public Sans', sans-serif

	:global(img)
		object-fit: cover

	:global(.icon)
		width: 24px
		height: 24px

	// Text Styles

	:global(p) 
		font-size: 16px
		font-weight: 500
		line-height: 24px
		letter-spacing: 0.1px

	:global(h1) 
		font-size: 24px
		font-weight: 600
		line-height: 32px
		font-family: 'Archivo', sans-serif
		font-variation-settings: 'wdth' 125

	:global(h2)
		font-family: 'Public Sans'
		font-style: normal
		font-weight: 500
		font-size: 22px
		line-height: 28px

	:global(a)
		text-decoration: none
		color: var(--on-background)

	// Feed

	.feed
		padding: 16px
		padding-top: 80px
		
	section
		display: flex
		gap: 8px
		flex-direction: column
		margin-bottom: 16px

	.carousel
		display: flex
		gap: 0px
		width: 100vw
		margin-left: -16px
		padding: 0 16px
		gap: 8px
		flex-flow: row nowrap
		scroll-snap-type: x mandatory
		overflow-x: scroll

	// Popular

	.movie-poster
		position: relative
		height: 211px
		min-width: 135px
		border-radius: 16px
		border: 2px solid var(--surface-1)
		overflow: hidden
		
		img
			height: 100%
			width: 100%
</style>
