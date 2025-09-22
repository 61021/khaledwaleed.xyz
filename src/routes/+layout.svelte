<script lang="ts">
	import '../app.css';
	import { page } from '$app/stores';

	let { children } = $props();

	const navigation = [
		{ name: 'Home', href: '/' },
		{ name: 'About', href: '/about' },
		{ name: 'Likes', href: '/likes' }
	];

	function isCurrentPage(href: string, currentPath: string): boolean {
		return href === currentPath || (href === '/' && currentPath === '/');
	}
</script>

<div class="min-h-screen bg-black text-white">
	<!-- Navigation -->
	<nav class="border-b border-gray-800 bg-black/95 backdrop-blur">
		<div class="mx-auto max-w-4xl px-6 sm:px-8">
			<div class="flex h-16 items-center justify-between">
				<div class="flex items-center space-x-8">
					<a href="/" class="text-xl font-semibold tracking-wide text-green-400"> khaled@dev:~$ </a>
					<div class="hidden space-x-6 sm:flex">
						{#each navigation as item}
							<a
								href={item.href}
								class="text-sm transition-colors duration-200 {isCurrentPage(
									item.href,
									$page.url.pathname
								)
									? 'border-b border-green-400 text-green-300'
									: 'text-gray-400 hover:text-white'}"
							>
								./{item.name.toLowerCase()}
							</a>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</nav>

	<!-- Main Content -->
	<main class="mx-auto max-w-4xl px-6 py-12 sm:px-8">
		{@render children()}
	</main>
</div>
