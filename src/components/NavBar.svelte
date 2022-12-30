<script>
	let lastScrollTop = 0;
	let windowOffset;
	let nav;

	const toggleNav = () => {
		let st = windowOffset.pageYOffset || document.documentElement.scrollTop;
		if (st > lastScrollTop) {
			nav.style.bottom = '-100%';
		} else {
			nav.style.bottom = '0';
		}
		lastScrollTop = st;
	};
</script>

<svelte:window on:scroll={toggleNav} bind:scrollY={windowOffset} />

<nav bind:this={nav}>
	<a class="tab active" href="/">
		<div class="iconContainer">
			<img src="icons/home.svg" alt="Home icon" />
		</div>
		<p>Home</p>
	</a>
	<a class="tab" href="explore">
		<div class="iconContainer">
			<img src="icons/explore.svg" alt="Explore icon" />
		</div>
		<p>Explore</p>
	</a>
</nav>

<style lang="sass">
	nav
		position: fixed
		bottom: 0
		left: 0
		z-index: 9
		display: flex
		justify-content: space-evenly
		width: 100vw
		background: var(--surface-1)
		padding: 16px
		padding-top: 12px
		transition: bottom .65s ease

		p
			font-style: normal
			font-weight: 500
			font-size: 12px
			line-height: 16px
			text-align: center
			letter-spacing: 0.5px

		.tab
			position: relative
			display: flex
			flex-direction: column
			align-items: center
			gap: 8px

			.iconContainer
				display: flex
				align-items: center
				justify-content: center
				width: 64px
				height: 32px
				background: none
				border-radius: 16px
				z-index: -1
				transition: all .4s ease

			&.active .iconContainer
				background: var(--surface-2)
</style>
