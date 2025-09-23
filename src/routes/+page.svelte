<script lang="ts">
	import { onMount } from 'svelte';

	// Terminal simulation state
	let terminalText = $state('');
	let showCursor = $state(true);
	let commandIndex = $state(0);

	const commands = [
		'$ whoami',
		'khaled',
		'$ ps aux | grep engineer',
		'khaled     1337  0.0  0.2  senior_dev  typescript',
		'$ cat ~/.profile',
		'export ROLE="Senior Software Engineer"',
		'export STACK="TypeScript,SvelteKit,Nuxt,Golang"',
		'export EXPERIENCE="5+ years"',
		'$ git log --oneline --author="khaled" | head -3',
		'a1b2c3d Building scalable systems at Qi',
		'4e5f6g7 Architecting frontend at Vitex',
		'8h9i0j1 Optimizing performance across stack',
		'$ uptime',
		'Currently: SvelteKit/Nuxt frontends + Go backends',
		'$ _'
	];

	onMount(() => {
		// Cursor blinking
		const cursorInterval = setInterval(() => {
			showCursor = !showCursor;
		}, 500);

		// Terminal typing animation
		let currentCommand = 0;
		let currentChar = 0;

		const typeCommand = () => {
			if (currentCommand < commands.length) {
				if (currentChar < commands[currentCommand].length) {
					terminalText += commands[currentCommand][currentChar];
					currentChar++;
					setTimeout(typeCommand, Math.random() * 50 + 30);
				} else {
					terminalText += '\n';
					currentCommand++;
					currentChar = 0;
					setTimeout(typeCommand, 800);
				}
			}
		};

		setTimeout(typeCommand, 1000);

		return () => {
			clearInterval(cursorInterval);
		};
	});
</script>

<svelte:head>
	<title>Khaled Waleed - Senior Software Engineer</title>
	<meta
		name="description"
		content="Senior Software Engineer specializing in modern web technologies at Qi and Vitex"
	/>
</svelte:head>

<div class="animate-fade-in space-y-8">
	<!-- Terminal Hero Section -->

	<section class="space-y-8 md:col-span-2">
		<!-- Terminal Window -->
		<div>
			<!-- Terminal Header -->

			<div class="flex items-center justify-between rounded-t-lg bg-slate-900 px-4 py-3">
				<div class="flex space-x-2">
					<div class="h-3 w-3 rounded-full bg-red-600"></div>
					<div class="h-3 w-3 rounded-full bg-yellow-600"></div>
					<div class="h-3 w-3 rounded-full bg-green-600"></div>
				</div>
				<div class="text-sm text-slate-300">khaled@arch:~$</div>
				<div class="w-16"></div>
			</div>

			<!-- Terminal Content -->
			<div
				class="min-h-[400px] overflow-hidden rounded-b-lg border border-slate-800 bg-black p-6 text-sm"
			>
				<div class="text-white">
					<pre class="leading-relaxed whitespace-pre-wrap">{terminalText}</pre>
					<span class="text-green-400" class:opacity-100={showCursor} class:opacity-0={!showCursor}
						>█</span
					>
				</div>
			</div>
		</div>

		<!-- Core Skills -->
		<div class="flex flex-wrap gap-4">
			<div
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-6 transition-all duration-300 hover:border-green-400 hover:shadow-lg hover:shadow-green-400/10"
			>
				<div class="mb-4 flex items-center space-x-3">
					<div class="font-mono text-xl text-green-400">{'</>'}</div>
					<h3 class="text-lg font-semibold text-white">Frontend</h3>
				</div>
				<p class="text-sm text-slate-300">
					SvelteKit, Nuxt.js, TypeScript. Blazingly fast, modern apps.
				</p>
			</div>

			<div
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-6 transition-all duration-300 hover:border-cyan-400 hover:shadow-lg hover:shadow-cyan-400/10"
			>
				<div class="mb-4 flex items-center space-x-3">
					<div class="font-mono text-xl text-cyan-400">[GO]</div>
					<h3 class="text-lg font-semibold text-white">Backend</h3>
				</div>
				<p class="text-sm text-slate-300">
					Golang services, APIs. speedy, concurrent, reliable systems.
				</p>
			</div>
			<div
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-6 transition-all duration-300 hover:border-violet-400 hover:shadow-lg hover:shadow-violet-400/10"
			>
				<div class="mb-4 flex items-center space-x-3">
					<div class="font-mono text-xl text-violet-400">[#]</div>
					<h3 class="text-lg font-semibold text-white">DevOps</h3>
				</div>
				<p class="text-sm text-slate-300">
					Docker, K8s, CI/CD, Arch Linux. Infrastructure that just works.
				</p>
			</div>
		</div>
	</section>

	<!-- About -->
	<section class="mx-auto max-w-2xl space-y-6 text-center">
		<div class="flex justify-center">
			<a
				href="/about"
				class="inline-flex items-center rounded-md border border-green-400 bg-slate-900 px-6 py-3 text-sm font-medium text-green-400 shadow-lg transition-all duration-200 hover:bg-green-400 hover:text-black hover:shadow-green-400/20"
			>
				<span class="mr-2">$</span>
				cat about.txt
				<svg class="ml-2 h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M13 7l5 5m0 0l-5 5m5-5H6"
					/>
				</svg>
			</a>
		</div>
	</section>
</div>
