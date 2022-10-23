<script>

import App from "src/App.svelte";

const app = new App({
	target: document.body,
	props: {
		// we'll learn about props later
		answer: 42
	}
});

</script>