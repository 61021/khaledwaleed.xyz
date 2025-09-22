<script lang="ts">
	// About page component using SvelteKit 5 runes

	const experiences = [
		{
			title: 'Senior Software Engineer',
			company: 'Qi',
			period: 'Current',
			description:
				'Building SvelteKit applications and Go microservices for scalable web platforms.',
			url: 'https://qi.iq'
		},
		{
			title: 'Senior Software Engineer',
			company: 'Vitex',
			period: 'Current',
			description: 'Developing Nuxt.js frontends and optimizing Golang backend performance.',
			url: 'https://vitex.dev'
		}
	];

	const skills = {
		Frontend: ['TypeScript', 'SvelteKit', 'Nuxt.js', 'Tailwind CSS', 'Vite'],
		Backend: ['Golang', 'PostgreSQL', 'Redis', 'REST APIs', 'Microservices'],
		DevOps: ['Docker', 'Kubernetes', 'CI/CD', 'Git', 'AWS'],
		System: ['Arch Linux', 'Bash', 'Systemd', 'Nginx', 'SSH']
	};
</script>

<svelte:head>
	<title>About - Khaled Waleed</title>
	<meta
		name="description"
		content="Learn more about Khaled Waleed, Senior Software Engineer with expertise in modern web technologies"
	/>
</svelte:head>

<div class="animate-fade-in space-y-16">
	<!-- Page Header -->
	<section class="space-y-8 text-center">
		<div class="space-y-4">
			<h1 class="text-4xl font-bold tracking-tight text-stone-200 sm:text-5xl">
				<code class="rounded border border-stone-700 bg-stone-800 px-4 py-2">man khaled</code>
			</h1>
			<div
				class="mx-auto max-w-3xl rounded-lg border border-stone-700 bg-stone-900/50 p-6 text-left text-sm"
			>
				<div class="mb-4 text-stone-300">KHALED(1) Developer Manual KHALED(1)</div>
				<div class="space-y-2 text-stone-300">
					<div><span class="font-bold text-green-400">NAME</span></div>
					<div class="ml-8">khaled - Senior Software Engineer, Full-stack Developer</div>
					<div class="mt-4"><span class="font-bold text-green-400">SYNOPSIS</span></div>
					<div class="ml-8">khaled [--frontend] [--backend] [--fullstack] [--remote]</div>
					<div class="mt-4"><span class="font-bold text-green-400">DESCRIPTION</span></div>
					<div class="ml-8">
						Experienced software engineer specializing in modern web development.
					</div>
					<div class="ml-8">Builds scalable applications using SvelteKit, Nuxt, and Golang.</div>
					<div class="ml-8">Currently contributing to projects at Qi and Vitex,</div>
					<div class="ml-8">focusing on user experience and system reliability.</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Background -->
	<section class="mx-auto max-w-3xl space-y-6">
		<h2 class="border-b border-stone-800 pb-2 text-2xl font-semibold text-stone-200">
			<code class="rounded bg-stone-800 px-2 py-1">cat ~/background.txt</code>
		</h2>
		<div class="space-y-6">
			<div class="rounded-lg border border-stone-700 bg-stone-900/30 p-6">
				<p class="mb-4 leading-relaxed text-stone-300">
					5+ years of experience building web applications that scale. I focus on writing clean,
					maintainable code and creating user experiences that solve real problems.
				</p>
				<p class="leading-relaxed text-stone-400">
					Currently working with talented teams at
					<a
						href="https://qi.iq"
						target="_blank"
						rel="noopener"
						class="border-b border-stone-600 text-stone-300 transition-colors hover:text-stone-200"
						>Qi</a
					>
					and
					<a
						href="https://vitex.dev"
						target="_blank"
						rel="noopener"
						class="border-b border-stone-600 text-stone-300 transition-colors hover:text-stone-200"
						>Vitex</a
					>, building modern applications with SvelteKit frontends and Go backends.
				</p>
			</div>
		</div>
	</section>

	<!-- Experience -->
	<section class="mx-auto max-w-3xl space-y-6">
		<h2 class="border-b border-stone-800 pb-2 text-2xl font-semibold text-stone-200">
			<code class="rounded bg-stone-800 px-2 py-1">ls ~/experience/</code>
		</h2>
		<div class="space-y-6">
			{#each experiences as exp}
				<div
					class="rounded-lg border border-stone-700 bg-stone-900/30 p-6 transition-all hover:border-stone-600"
				>
					<div class="mb-3 flex flex-col sm:flex-row sm:items-center sm:justify-between">
						<h3 class="text-xl font-semibold text-stone-200">
							{exp.title}
						</h3>
						<span class="mt-1 text-sm text-stone-400 sm:mt-0">
							{exp.period}
						</span>
					</div>
					<div class="mb-3">
						<a
							href={exp.url}
							target="_blank"
							rel="noopener"
							class="border-b border-stone-600 text-lg text-stone-300 transition-colors hover:border-stone-500 hover:text-stone-200"
						>
							{exp.company}
						</a>
					</div>
					<p class="text-sm leading-relaxed text-stone-400">
						{exp.description}
					</p>
				</div>
			{/each}
		</div>
	</section>

	<!-- Skills -->
	<section class="mx-auto max-w-3xl space-y-6">
		<h2 class="border-b border-stone-800 pb-2 text-2xl font-semibold text-stone-200">
			<code class="rounded bg-stone-800 px-3 py-1">find ~/skills -type f</code>
		</h2>

		<!-- Terminal-style skills listing -->
		<div class="rounded-lg border border-stone-700 bg-stone-900/30 p-6 text-sm">
			<div class="mb-4 text-stone-300">Available technologies and tools:</div>
			{#each Object.entries(skills) as [category, items]}
				<div class="mb-6">
					<div class="mb-2 text-stone-300">
						<span class="text-green-400">drwxr-xr-x</span> 2 khaled dev 4096 Sep 22 2025
						<span class="text-blue-400">{category.toLowerCase()}/</span>
					</div>
					<div class="ml-8 space-y-1">
						{#each items as skill}
							<div
								class="group cursor-pointer rounded px-2 py-1 text-stone-400 transition-all hover:bg-stone-800/50 hover:text-stone-300"
							>
								<span class="text-green-400">-rw-r--r--</span>
								<span class="text-stone-400">1 khaled dev</span>
								<span class="rounded px-1 group-hover:bg-stone-700/50 group-hover:text-stone-200"
									>{skill}</span
								>
							</div>
						{/each}
					</div>
				</div>
			{/each}
		</div>

		<!-- Interactive Commands -->
		<div class="grid grid-cols-1 gap-4 md:grid-cols-2">
			<div
				class="rounded-lg border border-stone-700 bg-stone-900/50 p-4 transition-all duration-300 hover:border-stone-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ which editor</div>
					<div class="text-stone-300">/usr/bin/nvim</div>
					<div class="mt-2 text-xs text-stone-400">Vim user since 2019 [>_]</div>
				</div>
			</div>

			<div
				class="rounded-lg border border-stone-700 bg-stone-900/50 p-4 transition-all duration-300 hover:border-stone-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ echo $SHELL</div>
					<div class="text-stone-300">/usr/bin/fish</div>
					<div class="mt-2 text-xs text-stone-400">Fish shell {'><(((°>'}</div>
				</div>
			</div>

			<div
				class="rounded-lg border border-stone-700 bg-stone-900/50 p-4 transition-all duration-300 hover:border-stone-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ uname -r</div>
					<div class="text-stone-300">6.16.8-arch1-1</div>
					<div class="mt-2 text-xs text-stone-400">Arch Linux BTW ^_^</div>
				</div>
			</div>

			<div
				class="rounded-lg border border-stone-700 bg-stone-900/50 p-4 transition-all duration-300 hover:border-stone-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ go version</div>
					<div class="text-stone-300">go version go1.21.0 linux/amd64</div>
					<div class="mt-2 text-xs text-stone-400">Gopher for life \o/</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Contact -->
	<section class="mx-auto max-w-3xl space-y-6 border-t border-stone-800 pt-12">
		<h2 class="text-center text-2xl font-semibold text-stone-200">
			<code class="rounded border border-stone-700 bg-stone-800 px-3 py-1">./get_in_touch.sh</code>
		</h2>

		<!-- Contact Info -->
		<div class="rounded-lg border border-stone-700 bg-stone-900/30 p-6 text-sm">
			<div class="space-y-2">
				<div class="text-green-400">$ curl -s https://api.khaled.dev/contact</div>
				<div class="text-stone-300">{'{'}</div>
				<div class="ml-4 text-stone-300">
					"status": "<span class="text-green-300">available</span>",
				</div>
				<div class="ml-4 text-stone-300">
					"email": "<span class="text-blue-300">khaled@example.com</span>",
				</div>
				<div class="ml-4 text-stone-300">
					"linkedin": "<span class="text-blue-300">linkedin.com/in/khaledwaleed</span>",
				</div>
				<div class="ml-4 text-stone-300">
					"github": "<span class="text-blue-300">github.com/khaledwaleed</span>",
				</div>
				<div class="ml-4 text-stone-300">
					"location": "<span class="text-green-300">remote-friendly</span>",
				</div>
				<div class="ml-4 text-stone-300">
					"interests": ["<span class="text-yellow-300">web development</span>", "<span
						class="text-yellow-300">scalable systems</span
					>", "<span class="text-yellow-300">clean code</span>"]
				</div>
				<div class="text-stone-300">{'}'}</div>
				<div class="mt-4 text-green-400">$ echo "Let's build something great together"</div>
				<div class="text-stone-300">Let's build something great together</div>
			</div>
		</div>

		<!-- Contact Buttons -->
		<div class="flex flex-col justify-center gap-4 sm:flex-row">
			<a
				href="mailto:khaled@example.com"
				class="inline-flex items-center justify-center rounded-md border border-stone-600 bg-stone-800 px-6 py-3 text-sm font-medium text-stone-200 shadow-lg transition-all duration-200 hover:bg-stone-700"
			>
				<span class="mr-2">$</span>
				echo "Hello" | mail khaled
			</a>
			<a
				href="/"
				class="inline-flex items-center justify-center rounded-md border border-stone-600 px-6 py-3 text-sm font-medium text-stone-300 transition-all duration-200 hover:bg-stone-800/50"
			>
				<span class="mr-2">$</span>
				cd ~
			</a>
		</div>

		<!-- Footer -->
		<div class="text-center text-sm text-stone-500">
			<div class="mt-8 rounded border border-stone-700 bg-stone-900/20 p-4">
				<span class="text-stone-400">"Code is poetry written for machines to understand."</span>
			</div>
		</div>
	</section>
</div>
