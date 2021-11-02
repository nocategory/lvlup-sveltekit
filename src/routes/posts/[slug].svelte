<script context="module">
	export async function load({ page }) {
		const post = {
			title: page.params.slug,
			body: 'lorem ipsum dolor sit amet'
		};
		return {
			props: { post }
		};
	}
</script>

<script>
	export let post;
</script>

<h1 class="text-3xl">{post.title}</h1>
<h4>{post.body}</h4>
