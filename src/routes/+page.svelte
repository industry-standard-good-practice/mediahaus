<script>
	import FriendCard from '../components/FriendCard.svelte';
	import TopBar from '../components/TopBar.svelte';
</script>

<TopBar />
<div class="feed">
	<section>
		<h1>For You</h1>
		<div class="carousel">
			<a class="for-you-card active" href="somewhere">
				<h2>Shawshank Redemption</h2>
				<p>89% Rotten Tomatoes</p>
				<img src="somewhere" alt="backgroundImage" />
			</a>
			<a class="for-you-card" href="somewhere">
				<h2>Shawshank Redemption</h2>
				<p>89% Rotten Tomatoes</p>
				<img src="somewhere" alt="backgroundImage" />
			</a>
		</div>
	</section>
	<section>
		<h1>Popular Right Now</h1>
		<div class="carousel">
			<a href="somewhere" class="movie-poster">
				<img src="somewhere" alt="Poster of Inception" />
			</a>
			<a href="somewhere" class="movie-poster">
				<img src="somewhere" alt="Poster of Inception" />
			</a>
			<a href="somewhere" class="movie-poster">
				<img src="somewhere" alt="Poster of Inception" />
			</a>
			<a href="somewhere" class="movie-poster">
				<img src="somewhere" alt="Poster of Inception" />
			</a>
			<a href="somewhere" class="movie-poster">
				<img src="somewhere" alt="Poster of Inception" />
			</a>
		</div>
	</section>
	<section>
		<h1>Friends</h1>
		<FriendCard />
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

	// For You

	.for-you-card
		position: relative
		flex: 0
		min-width: calc( 100vw - 32px )
		height: 224px
		display: flex
		flex-direction: column
		justify-content: flex-end
		padding: 16px
		border-radius: 16px
		scroll-snap-align: center
		background: rgba(255, 255, 255, .1)

		&.active
			border: 1px solid var(--primary)
			filter: drop-shadow(0px 4px 20px rgba(255, 170, 242, 0.25))

		img
			position: absolute
			top: 0
			left: 0
			width: 100%
			height:100%

	// Popular

	.movie-poster
		border-radius: 16px
		border: 2px solid var(--surface-1)
		
		img
			min-height: 211px
			min-width: 135px
</style>
