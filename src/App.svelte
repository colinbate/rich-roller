<script lang="ts">
	import ModeSwitcher from './ModeSwitcher.svelte';
	import Tailwindcss from './Tailwindcss.svelte';
	import { Table } from 'svelte-dice';

	let total: number;
	function roll(ev: CustomEvent) {
		total = ev.detail.sum;
	}
</script>
<Tailwindcss />
<ModeSwitcher />
<main class="p-4 mx-auto text-center max-w-3xl">
	<h1 class="uppercase text-6xl leading-normal font-thin text-svelte mb-4">Rich Roller</h1>
	<Table numberOfDice={3} on:rolled={roll}></Table>
	<div class="">{#if total}Total: {total}{:else}Click to roll...{/if}</div>
</main>