<script context="module">
	export async function load() {
		let postsInfo = [];
		const posts = import.meta.globEager('../../posts/*.md');
		for (const [path, info] of Object.entries(posts)) {
			postsInfo.push({
				// turns an ugly ../../posts.hi.md that won't be properly navigated to into a "hi"
				fileName: path.split('/').pop().replace('.md', ''),
				title: info.metadata.title
			});
		}
		return {
			props: { postsInfo }
		};
	}
</script>

<script>
	export let postsInfo;
</script>

<a href="/posts" class="p-2 text-blue-500">Posts</a>
<h2>Archive</h2>
<ul>
	{#each postsInfo as postInfo}
		<li><a href={`/posts/${postInfo.fileName}`}>{postInfo.title}</a></li>
	{/each}
</ul>

<slot />
