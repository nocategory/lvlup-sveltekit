<script context="module">
	export async function load({ page }) {
		// https://github.com/sveltejs/kit/issues/1326
		// kinda broken, but this sort of works 👇
		try {
			const Post = await import(`../../posts/${page.params.slug}.md`);

			return {
				props: { Post: Post.default }
			};
		} catch (e) {
			return {
				status: 404,
				error: 'NOT FOUND'
			};
		}
	}
</script>

<script>
	export let Post;
</script>

<h3>Post:</h3>

<!-- https://svelte.dev/docs#svelte_component -->
<svelte:component this={Post} />
