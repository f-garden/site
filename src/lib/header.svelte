<script lang="ts">
	import Dropdown from './dropdown.svelte';

	const projects = [{ name: 'Rede Memória', url: 'https://redememoria.org/' }];
	const links = [
		{ name: 'e-mail', url: 'mailto:f.garden.lx@gmail.com' },
		{ name: 'Instagram', url: 'https://www.instagram.com/f.gardn/' }
	];
</script>

<header class="fixed top-0 left-0 w-full flex items-center justify-between p-4">
	<span class="text-xl font-bold nowrap flex items-center gap-4">
		<img src="/assets/fgarden.svg" alt="f.gardn logo" class="h-10" />
		f.gardn
	</span>

	<div class="menu-right relative">
		<Dropdown links={projects}>Projetos</Dropdown>
		<Dropdown {links}>Contacto</Dropdown>
	</div>
</header>
