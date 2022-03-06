<script context="module">
	/** @type {import('@sveltejs/kit').ErrorLoad} */
	export function load({ error}) {
		return {
			props: { message: error.message }
		};
	}
</script>

<script>
	/** @type {number} */

	/** @type {Error & {frame?: string} & {loc?: object}} */
	export let message;
</script>

<div class="error">
    <h2>Oops! </h2>
    <p>{message}</p>
    <a href="/">Go to Home</a>
</div>
<style>
    .error{
        min-height: 40vh;
        text-align: center;
    }
    a{
        text-decoration: none;
    }
</style>

