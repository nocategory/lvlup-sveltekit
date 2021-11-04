<script context="module">
	export async function load({ page }) {
		// https://github.com/sveltejs/kit/issues/1326
		// kinda broken, but this sort of works 👇
		const Post = await import(`${page.params.slug}.md`).default;

		return {
			props: { Post }
		};
	}
</script>

<script>
	let Post;
</script>

<h3 class="text-2xl">Markdown:</h3>
<Post />
