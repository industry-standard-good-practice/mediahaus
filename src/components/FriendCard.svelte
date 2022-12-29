<script>
	import { fly, fade } from 'svelte/transition';
	export let user = {
		username: 'Jack Trego',
		profilePic:
			'https://images.pexels.com/photos/3222422/pexels-photo-3222422.jpeg?auto=compress&cs=tinysrgb&h=650&w=940'
	};
	export let likeCount = 0;
	export let userReview = {
		title: 'Pulp Fiction',
		rating: '8.5',
		review: 'Bloody and gory. Fun time.',
		poster:
			'https://images.pexels.com/photos/10705224/pexels-photo-10705224.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500'
	};

	let isLiked = false;

	const likeCountChange = () => {
		if (isLiked) {
			isLiked = false;
			likeCount--;
		} else {
			isLiked = true;
			likeCount++;
		}
	};
</script>

<div class="cardContain">
	<div class="topBar">
		<div class="left">
			<img class="profilePic" src={user.profilePic} alt="User profile" />
			<p>{user.username}</p>
		</div>
		<div class="right" on:click={likeCountChange} on:keydown={likeCountChange}>
			{#key likeCount}
				<p in:fly={{ y: -20, duration: 200 }} out:fly={{ y: 10, duration: 200 }}>
					{likeCount}
				</p>
			{/key}
			{#if isLiked}
				<img
					class="icon"
					src="icons/like-full.svg"
					alt="Like button"
					transition:fade={{ duration: 200 }}
				/>
			{:else}
				<img
					class="icon"
					src="icons/like-empty.svg"
					alt="Like button"
					transition:fade={{ duration: 200 }}
				/>
			{/if}
		</div>
	</div>
	<div class="content">
		<img class="poster" src={userReview.poster} alt="Movie poster" />
		<div class="text">
			<p style="font-weight: 800 letter-spacing: 0.5px">
				{userReview.title}
			</p>
			<p style="margin-bottom: 16px">
				{userReview.rating} / 10
			</p>
			<h1>{userReview.review}</h1>
		</div>
	</div>
</div>

<style lang="sass">
	.cardContain 
		width: 100%
		border: 2px solid var(--surface-1)
		border-radius: 16px
		overflow: hidden
		cursor: pointer
		background: var(--background)
		position: relative

	.content 
		padding: 16px
		padding-top: 0px
		display: flex
		gap: 16px
	
	.poster 
		width: 135px
		height: 210px
		border: 1px solid var(--read-only--dark--surface3)
		border-radius: 8px
	
	.profilePic 
		width: 40px
		height: 40px
		border-radius: 20px

	.topBar 
		padding: 16px
		display: flex
		align-items: center
		justify-content: space-between
	
	.topBar .left,
	.topBar .right 
		display: flex
		flex-direction: row
		align-items: center
		justify-content: center
		gap: 8px
		position: relative
	
	.right 
		height: 24px

		p 
			position: absolute
			right: 32px
			top: 0px
			text-align: center
	
	.text 
		width: max-content
	
	.icon 
		position: absolute
		right: 0
		top: 0
</style>
