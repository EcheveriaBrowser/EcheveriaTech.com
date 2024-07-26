<script lang="ts">
	import { onMount } from 'svelte';

	let dark: boolean;

	onMount(() => {
		setMode(true);  // Set dark mode on mount
	});

	function setMode(value: boolean) {
		dark = value;

		if (dark) document.documentElement.classList.add('dark');
		else document.documentElement.classList.remove('dark');

		localStorage.theme = dark ? 'dark' : 'light';
	}
</script>

<svelte:head>
	<script>
		// Ensure dark mode is always enabled on initial load
		document.documentElement.classList.add('dark');
		localStorage.theme = 'dark';
	</script>
</svelte:head>
