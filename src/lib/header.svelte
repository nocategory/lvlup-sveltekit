<header>
	<nav>
		<ul>
			<li><a sveltekit:prefetch href="/">Home</a></li>
			<li><a sveltekit:prefetch href="/about">About Us</a></li>
			<li><a sveltekit:prefetch href="/posts">Posts</a></li>
		</ul>
	</nav>
</header>

<style>
	nav {
		display: flex;
		align-items: center;
		justify-content: center;
	}
	nav > ul {
		display: flex;
		flex-direction: row;
	}
	nav > ul > li {
		display: block;
		padding: 1rem;
	}
</style>
