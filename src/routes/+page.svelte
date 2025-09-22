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

<div class="animate-fade-in space-y-16">
	<!-- Terminal Hero Section -->
	<section class="space-y-8">
		<!-- Terminal Window -->
		<div class="mx-auto max-w-4xl">
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
			<div class="min-h-[400px] rounded-b-lg border border-slate-800 bg-black p-6 text-sm">
				<div class="text-white">
					<pre class="leading-relaxed whitespace-pre-wrap">{terminalText}</pre>
					<span class="text-green-400" class:opacity-100={showCursor} class:opacity-0={!showCursor}
						>█</span
					>
				</div>
			</div>
		</div>

		<!-- Core Skills -->
		<div class="mx-auto grid max-w-4xl grid-cols-1 gap-6 md:grid-cols-3">
			<div
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-6 transition-all duration-300 hover:border-green-400 hover:shadow-lg hover:shadow-green-400/10"
			>
				<div class="mb-4 flex items-center space-x-3">
					<div class="font-mono text-xl text-green-400">{'</>'}</div>
					<h3 class="text-lg font-semibold text-white">Frontend</h3>
				</div>
				<p class="text-sm text-slate-300">
					SvelteKit, Nuxt.js, TypeScript. Building fast, modern web applications.
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
					Golang services, APIs, microservices. Fast, concurrent, reliable systems.
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
		<div class="rounded-lg border border-slate-700 bg-slate-900/30 p-6">
			<p class="text-lg leading-relaxed text-slate-200">
				Senior Software Engineer specializing in SvelteKit/Nuxt frontends and Go backends. Currently
				building scalable applications at Qi and Vitex.
			</p>
		</div>

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

	<!-- Tech Stack -->
	<section class="border-t border-slate-800 pt-12">
		<div class="space-y-8">
			<h2 class="text-center text-2xl font-semibold text-white">
				<code class="rounded border border-slate-700 bg-slate-900 px-3 py-1 text-green-400"
					>cat /etc/tech-stack</code
				>
			</h2>

			<!-- Technologies -->
			<div class="mx-auto max-w-4xl rounded-lg border border-slate-700 bg-black/60 p-6">
				<div class="space-y-4 text-sm">
					{#each [{ name: 'TypeScript', level: 95, command: 'tsc --strict --noEmit' }, { name: 'SvelteKit', level: 98, command: 'npm run dev' }, { name: 'Nuxt.js', level: 90, command: 'npm run build' }, { name: 'Golang', level: 85, command: 'go run main.go' }, { name: 'Docker/K8s', level: 80, command: 'docker compose up -d' }, { name: 'PostgreSQL', level: 75, command: 'psql -U postgres' }, { name: 'Arch Linux', level: 100, command: 'sudo pacman -Syu' }] as tech}
						<div
							class="group cursor-pointer rounded p-3 transition-all hover:border-l-4 hover:border-l-green-400 hover:bg-slate-800/50"
						>
							<div class="mb-2 flex items-center justify-between">
								<span class="text-xs text-green-400">$ {tech.command}</span>
								<span class="text-white">{tech.level}%</span>
							</div>
							<div class="h-2 w-full rounded-full bg-slate-800">
								<div
									class="h-2 rounded-full bg-gradient-to-r from-slate-600 to-slate-500 transition-all duration-1000 group-hover:from-green-400 group-hover:to-cyan-400 group-hover:shadow-lg group-hover:shadow-green-400/30"
									style="width: {tech.level}%"
								></div>
							</div>
							<div class="mt-1 text-xs text-slate-400 transition-colors group-hover:text-white">
								{tech.name}
							</div>
						</div>
					{/each}
				</div>
			</div>

			<!-- Current Status -->
			<div class="mx-auto max-w-2xl rounded-lg border border-slate-700 bg-slate-900/60 p-6">
				<div class="flex items-center space-x-4 text-sm">
					<div class="flex items-center space-x-2">
						<div
							class="h-3 w-3 animate-pulse rounded-full bg-green-400 shadow-lg shadow-green-400/50"
						></div>
						<span class="font-semibold text-green-400">STATUS: AVAILABLE FOR WORK</span>
					</div>
				</div>
				<div class="mt-4 space-y-1 text-sm text-slate-300">
					<div>
						<code class="text-cyan-400">Location:</code>
						<span class="text-white">Remote-friendly</span>
					</div>
					<div>
						<code class="text-cyan-400">Experience:</code>
						<span class="text-white">5+ years in production</span>
					</div>
					<div>
						<code class="text-cyan-400">Focus:</code>
						<span class="text-white">Full-stack web development</span>
					</div>
					<div>
						<code class="text-cyan-400">Stack:</code>
						<span class="text-white">SvelteKit + Go + PostgreSQL</span>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Likes -->
	<section class="border-t border-slate-800 pt-12">
		<div class="space-y-8">
			<h2 class="text-center text-2xl font-semibold text-white">
				<code class="rounded border border-slate-700 bg-slate-900 px-3 py-1 text-green-400"
					>grep -r "interests" ~/life/</code
				>
			</h2>

			<div class="mx-auto max-w-2xl text-center">
				<p class="mb-6 text-lg text-slate-300">Want to know what I'm into?</p>
				<a
					href="/likes"
					class="inline-flex items-center rounded-md border border-cyan-400 bg-slate-900 px-6 py-3 text-sm font-medium text-cyan-400 shadow-lg transition-all duration-200 hover:bg-cyan-400 hover:text-black hover:shadow-cyan-400/20"
				>
					<span class="mr-2">$</span>
					cat ~/interests.md
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
		</div>
	</section>
</div>
