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
	import Hi from '../../blogposts/hi.md';
	export let post;
</script>

<h1 class="text-3xl">{post.title}</h1>

<h3 class="text-2xl">Markdown:</h3>
<Hi />
