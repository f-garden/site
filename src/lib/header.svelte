<script lang="ts">
	import Dropdown from './dropdown.svelte';

	const projects = [{ name: 'Rede Memória', url: 'https://redememoria.org/' }];
	const links = [
		{ name: 'e-mail', url: 'mailto:f.garden.lx@gmail.com' },
		{ name: 'Instagram', url: 'https://www.instagram.com/f.garden/' }
	];
</script>

<header class="fixed top-0 left-0 w-full p-4">
	<div class="flex flex-wrap items-center justify-between gap-4">
		<div class="flex items-center gap-4 min-w-0">
			<img src="/assets/fgarden.svg" alt="f.garden logo" class="h-10 flex-shrink-0" />
			<span class="text-xl font-bold whitespace-nowrap">f.garden</span>
		</div>

		<div class="flex items-center gap-2 flex-wrap sm:flex-nowrap">
			<Dropdown links={projects}>Projetos</Dropdown>
			<Dropdown {links}>Contacto</Dropdown>
		</div>
	</div>
</header>
