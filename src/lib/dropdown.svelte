<script lang="ts">
	import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';

	let isDropdownOpen = false;
	const componentKey = (Math.random() + 1).toString(36).substring(7);

	export let links: { name: string; url: string }[] = [];

	// Close dropdown when clicking outside
	function handleClickOutside(event: MouseEvent) {
		if (isDropdownOpen && event.target && (event.target as Element).closest(`.${componentKey}`)) {
			return;
		}
		isDropdownOpen = false;
	}
</script>

<svelte:window on:click={handleClickOutside} />

<div class="{componentKey} relative inline-block">
	<button
		class="px-4 py-2 flex items-center gap-4 border-b border-transparent hover:border-current"
		on:click={() => (isDropdownOpen = !isDropdownOpen)}
	>
		<slot />
		{componentKey}
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
