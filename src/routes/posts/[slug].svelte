<script context="module">
	export async function load({ page }) {
		// https://github.com/sveltejs/kit/issues/1326
		// kinda broken, but this sort of works 👇
		const Post = await import(`../../posts/${page.params.slug}.md`);

		return {
			props: { Post: Post.default, title: Post.metadata.title }
		};
	}
</script>

<script>
	export let Post;
	export let title;
</script>

<h3 class="text-2xl">Markdown:</h3>

{title}

<Post />
