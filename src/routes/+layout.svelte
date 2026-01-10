<script lang="ts">
	import './layout.css';
	import "../app.css";

	import favicon from '$lib/assets/favicon.svg';
	import { ModeWatcher } from "mode-watcher";

	import * as Sidebar from "$lib/components/ui/sidebar/index.js";
	import * as Tooltip from "$lib/components/ui/tooltip/index.js";

	import AppSidebar from "$lib/components/app-sidebar.svelte";

	let { children } = $props();

	import SvelteSnow from "svelte-snow";
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<ModeWatcher />

<SvelteSnow active={false}>
	{@render children?.()}
</SvelteSnow>