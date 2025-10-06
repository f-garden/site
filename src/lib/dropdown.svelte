<script lang="ts">
	import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';

	let isDropdownOpen = false;
	let dropdownRef: HTMLDivElement;

	export let links: { name: string; url: string }[] = [];

	// Close dropdown when clicking outside
	function handleClickOutside(event: MouseEvent) {
		if (isDropdownOpen && dropdownRef && !dropdownRef.contains(event.target as Node)) {
			isDropdownOpen = false;
		}
	}
</script>

<svelte:window on:click={handleClickOutside} />

<div bind:this={dropdownRef} class="dropdown relative inline-block">
	<button
		class="px-4 py-2 flex items-center gap-4 border-b border-transparent hover:border-current"
		on:click={() => (isDropdownOpen = !isDropdownOpen)}
	>
		<slot />
		<span
			class="w-0 h-0 transform transition-transform duration-200 origin-[50%_75%]
          border-6 border-solid border-transparent border-b-current"
			class:rotate-180={isDropdownOpen}
		>
		</span>
	</button>
	{#if isDropdownOpen}
		<div
			class="dropdown-content absolute left-0 mt-2 z-50 overflow-hidden"
			transition:slide={{ duration: 300, easing: quintOut }}
		>
			{#each links as link, i}
				<a
					href={link.url}
					target="_blank"
					class="block px-4 py-3 border-b border-transparent hover:border-current text-nowrap"
					style="animation-delay: {i * 50}ms"
				>
					{link.name}
				</a>
			{/each}
		</div>
	{/if}
</div>
