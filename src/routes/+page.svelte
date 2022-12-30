<script>
	import ForYouCard from '../components/ForYouCard.svelte';
	import FollowingCard from '../components/FollowingCard.svelte';

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

	let forYouData = [
		{
			title: 'Babylon',
			score: '55% Rotten Tomatoes',
			src: 'https://download-video.akamaized.net/2/playback/af2084df-c699-46ed-8fdf-450e45d1754d/152e9f39-56d4d48d?__token__=st=1672424104~exp=1672438504~acl=%2F2%2Fplayback%2Faf2084df-c699-46ed-8fdf-450e45d1754d%2F152e9f39-56d4d48d%2A~hmac=7925a70ad1b810a5805fc5663b387dd6e7e5a5dafdcd01bcf8ea08024f5a388e&r=dXMtY2VudHJhbDE%3D'
		},
		{
			title: 'Her',
			score: '99% Rotten Tomatoes',
			src: 'https://vod-progressive.akamaized.net/exp=1672432727~acl=%2Fvimeo-prod-skyfire-std-us%2F01%2F4960%2F7%2F199804666%2F674256539.mp4~hmac=958c6e6f5dfb27a11aa23837800efd1893412718abebf580f6fe527c3f547ccc/vimeo-prod-skyfire-std-us/01/4960/7/199804666/674256539.mp4'
		},
		{
			title: 'The Batman',
			score: '89% Rotten Tomatoes',
			src: 'https://vod-progressive.akamaized.net/exp=1672438659~acl=%2Fvimeo-prod-skyfire-std-us%2F01%2F2101%2F26%2F660505832%2F3036337154.mp4~hmac=deafacc4c323fdb1ec0dfe692fa79374992bf636ea0c5df3d958eb728c27f7d2/vimeo-prod-skyfire-std-us/01/2101/26/660505832/3036337154.mp4?filename=file.mp4'
		}
	];

	let popularData = [
		{
			src: 'https://m.media-amazon.com/images/I/71uKM+LdgFL._AC_UF894,1000_QL80_.jpg',
			slug: 'Inception'
		},
		{
			src: 'https://m.media-amazon.com/images/I/61PXdxTJGPL.jpg',
			slug: 'Inglourious Basterds'
		},
		{
			src: 'https://m.media-amazon.com/images/I/51unGrb-AAL._AC_.jpg',
			slug: 'The Matrix'
		},
		{
			src: 'https://m.media-amazon.com/images/I/51SNtj+h-TL._AC_.jpg',
			slug: 'When Harry Met Sally'
		},
		{
			src: 'https://m.media-amazon.com/images/I/51u15I5bJDL._AC_UF894,1000_QL80_.jpg',
			slug: 'Hot Fuzz'
		}
	];
</script>

<div class="feed">
	<section>
		<h1>For You</h1>
		<div class="carousel">
			{#each forYouData as data}
				<ForYouCard {...data} />
			{/each}
		</div>
	</section>
	<section>
		<h1>Popular Right Now</h1>
		<div class="carousel">
			{#each popularData as data}
				<a href="movies/{data.slug}" class="movie-poster">
					<img src={data.src} alt="Poster of Inception" />
				</a>
			{/each}
		</div>
	</section>
	<section>
		<h1>Following</h1>
		{#each posts as post}
			<FollowingCard {...post} />
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
		--surface-2: #554050

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
		margin-top: -16px
		padding: 16px
		gap: 8px
		flex-flow: row nowrap
		scroll-snap-type: x mandatory
		overflow-x: scroll

	// Popular

	.movie-poster
		position: relative
		height: 211px
		min-width: 135px
		border-radius: 8px
		border: 2px solid var(--surface-1)
		overflow: hidden
		
		img
			height: 100%
			width: 100%
</style>
