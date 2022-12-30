<script>
	let lastScrollTop = 0;
	let windowOffset;
	let topBar;

	const toggleNav = () => {
		let st = windowOffset.pageYOffset || document.documentElement.scrollTop;
		if (st > lastScrollTop) {
			topBar.style.top = '-100%';
		} else {
			topBar.style.top = '0';
		}
		lastScrollTop = st;
	};
</script>

<svelte:window on:scroll={toggleNav} bind:scrollY={windowOffset} />

<div class="topBar" bind:this={topBar}>
	<img src="images/logo.svg" alt="logo" class="logo" />
	<form method="get" action="">
		<div class="searchBox">
			<img src="icons/search.svg" alt="search icon" class="searchIcon" />
			<input type="text" placeholder="Search..." />
		</div>
	</form>
	<img
		class="profilePic"
		alt="profile"
		src="https://images.pexels.com/photos/3226441/pexels-photo-3226441.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
	/>
</div>

<style lang="sass">
	.topBar 
		background: var(--background)
		width: 100vw
		display: flex
		height: 80px
		position: fixed
		top: 0
		left: 0
		z-index: 9
		padding: 16px
		box-sizing: border-box
		align-items: center
		justify-content: space-between
		gap: 16px
		transition: top .6s ease
	
	.logo 
		width: 64px
		height: 32px
	
	.profilePic 
		width: 32px
		height: 32px
		background: gray
		border-radius: 50%
	
	form 
		flex-grow: 1
		height: 100%
	
	.searchBox 
		display: flex
		align-items: center
		justify-content: center
		height: 100%
		background: var(--surface-1)
		border-radius: 12px
	
	input 
		width: 100%
		height: 100%
		margin: 0
		background: none
		border: none
		outline: none
		display: flex
		align-items: center
		font-size: 12px
		color: var(--on-background)
	
	::-webkit-input-placeholder 
		font-family: 'Public Sans', sans-serif
		font-weight: 500
		color: var(--on-background)
		letter-spacing: 0.5px
	
	.searchIcon 
		padding: 12px
		padding-right: 8px

</style>
