<script>
	export let user = {
		username: 'Jack Trego',
		profilePic:
			'https://images.pexels.com/photos/3222422/pexels-photo-3222422.jpeg?auto=compress&cs=tinysrgb&h=650&w=940',
	};
	export let likeCount = 0;
	export let userReview = {
		title: 'Pulp Fiction',
		rating: '8.5/10',
		review: 'Bloody and gory. Fun time.',
		poster: 'https://images.pexels.com/photos/10705224/pexels-photo-10705224.jpeg?auto=compress&cs=tinysrgb&dpr=2&w=500',
	};
</script>

<div class="cardContain">
	<div class="topBar">
		<div class="left">
			<img class="profilePic" src={user.profilePic} alt="User profile" />
			<p class="titleMedium">{user.username}</p>
		</div>
		<div class="right">
			<p class="titleMedium">{likeCount}</p>
			<img class="icon" src="icons/like-empty.svg" alt="Like button" />
		</div>
	</div>
	<div class="content">
		<img class="poster" src={userReview.poster} alt="Movie poster" />
		<div class="text">
			<p
				class="titleMedium"
				style="font-weight: 800; letter-spacing: 0.5px"
			>
				{userReview.title}
			</p>
			<p class="titleMedium" style="margin-bottom: 16px;">
				{userReview.rating}
			</p>
			<p class="headlineSmall">{userReview.review}</p>
		</div>
	</div>
</div>

<style>
	.cardContain {
		width: 100%;
		border: 1px solid var(--read-only--dark--surface3);
		border-radius: 16px;
		overflow: hidden;
		cursor: pointer;
		background: var(--sys--dark--surface);
		color: var(--sys--dark--on-surface);
		position: relative;
	}

	.content {
		padding: 16px;
		padding-top: 0px;
		display: flex;
		gap: 16px;
	}

	.poster {
		width: 135px;
		height: 210px;
		border: 1px solid var(--read-only--dark--surface3);
		border-radius: 16px;
	}

	.profilePic {
		width: 40px;
		height: 40px;
		border-radius: 20px;
	}

	.topBar {
		padding: 16px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.topBar .left,
	.topBar .right {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		gap: 8px;
	}

	.text {
		width: max-content;
	}

	p {
		margin: 0;
	}
</style>
