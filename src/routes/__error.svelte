<script context="module">
	export async function load({ error, status }) {
		return {
			props: {
				status,
				error: error.message
			}
		};
	}
</script>

<script>
	export let status;
	export let error;
</script>

<h1>OOPSIE!</h1>
<h3>{status}</h3>
<h4>{error}</h4>
