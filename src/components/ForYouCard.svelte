<script>
	import { inview } from 'svelte-inview';

	let isInView = false;
	let backgroundVideo;

	const options = {
		threshold: 0.5
	};

	const videoEnter = () => {
		isInView = true;
		backgroundVideo.play();
	};

	const videoLeave = () => {
		isInView = false;
		backgroundVideo.pause();
	};

	export let title = 'Shawshank Redemption';
	export let score = '89% Rotten Tomatoes';
	export let src = 'something';
</script>

<a
	class="for-you-card {isInView ? 'active' : ''}"
	href="somewhere"
	use:inview={options}
	on:enter={videoEnter}
	on:leave={videoLeave}
>
	<h2>{title}</h2>
	<p>{score}</p>
	<video {src} muted autoplay loop bind:this={backgroundVideo} />
</a>

<style lang="sass">
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
		overflow: hidden
		border: 1px solid rgba(0, 0, 0, 0)
		transition: all .8s ease

		&.active
			border: 1px solid var(--primary)
			filter: drop-shadow(0px 4px 6px rgba(255, 170, 242, 0.25))

		&::after
			content: ''
			position: absolute
			top: 0
			left: 0
			width: 100%
			height: 100%
			z-index: -1
			background: linear-gradient(180deg, rgba(0, 0, 0, 0) 50%, rgba(0, 0, 0, 0.8) 100%),

		video
			position: absolute
			top: 0
			left: 0
			width: 100%
			height:100%
			z-index: -2
			object-fit: cover
</style>
