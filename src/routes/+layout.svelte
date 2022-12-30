<script>
	import NavBar from '../components/NavBar.svelte';
	import TopBar from '../components/TopBar.svelte';
</script>

<TopBar />
<NavBar />
<main>
	<slot />
</main>

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

	:global(main)
		padding-top: 80px

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

</style>
