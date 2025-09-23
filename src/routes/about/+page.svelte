<script lang="ts">
	// About page component using SvelteKit 5 runes

	const experiences = [
		{
			title: 'Senior Software Engineer',
			company: 'Qi',
			period: 'Current',
			description: 'Leading the development of the frontend for multiple projects.',
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
		<div class="space-y-8">
			<h1 class="text-4xl font-bold tracking-tight text-white sm:text-5xl">
				<code class="rounded border border-slate-700 bg-slate-900 px-4 py-2 text-green-400"
					>man khaled</code
				>
			</h1>
			<div class="mx-auto rounded-lg border border-slate-700 bg-black/60 p-6 text-left text-sm">
				<div class="mb-4 text-slate-300">KHALED(1) Developer Manual KHALED(1)</div>
				<div class="space-y-2 text-slate-300">
					<div><span class="font-bold text-green-400">NAME</span></div>
					<div class="ml-8">khaled - Senior Software Engineer</div>
					<div class="mt-4"><span class="font-bold text-green-400">SYNOPSIS</span></div>
					<div class="ml-8">khaled [--frontend] [--backend]</div>
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
	<section class="mx-auto space-y-6">
		<code class="rounded border border-slate-700 bg-slate-900 px-2 py-1 text-green-400"
			>cat ~/background.txt</code
		>
		<div class="space-y-6">
			<div class="rounded-lg border border-slate-700 bg-slate-900/50 p-6">
				<p class="mb-4 leading-relaxed text-slate-200">
					5+ years of experience building web applications that scale. I focus on writing clean,
					maintainable code and creating user experiences that feel alive.
				</p>
				<p class="leading-relaxed text-slate-300">
					Currently working with talented teams at
					<a
						href="https://qi.iq"
						target="_blank"
						rel="noopener"
						class="border-b border-green-400 text-green-400 transition-colors hover:text-white"
						>Qi</a
					>
					and
					<a
						href="https://vitex.dev"
						target="_blank"
						rel="noopener"
						class="border-b border-green-400 text-green-400 transition-colors hover:text-white"
						>Vitex</a
					>, building modern applications with SvelteKit frontends and Go backends.
				</p>
			</div>
		</div>
	</section>

	<!-- Experience -->
	<section class="mx-auto space-y-6">
		<code class="rounded border border-slate-700 bg-slate-900 px-2 py-1 text-green-400"
			>ls ~/current/</code
		>
		<div class="space-y-6">
			{#each experiences as exp}
				<div
					class="rounded-lg border border-slate-700 bg-slate-900/50 p-6 transition-all hover:border-slate-600"
				>
					<div class="mb-3 flex flex-col sm:flex-row sm:items-center sm:justify-between">
						<h3 class="text-xl font-semibold text-white">
							{exp.title}
						</h3>
						<span class="mt-1 text-sm text-slate-400 sm:mt-0">
							{exp.period}
						</span>
					</div>
					<div class="mb-3">
						<a
							href={exp.url}
							target="_blank"
							rel="noopener"
							class="border-b border-green-400 text-lg text-green-400 transition-colors hover:border-white hover:text-white"
						>
							{exp.company}
						</a>
					</div>
					<p class="text-sm leading-relaxed text-slate-300">
						{exp.description}
					</p>
				</div>
			{/each}
		</div>
	</section>

	<!-- Skills -->
	<section class="mx-auto space-y-6">
		<code class="rounded border border-slate-700 bg-slate-900 px-3 py-1 text-green-400"
			>find ~/skills -type f</code
		>

		<!-- Terminal-style skills listing -->
		<div class="rounded-lg border border-slate-700 bg-black/60 p-6 text-sm">
			<div class="mb-4 text-slate-300">Available technologies and tools:</div>
			{#each Object.entries(skills) as [category, items]}
				<div class="mb-6">
					<div class="mb-2 text-slate-300">
						<span class="text-green-400">drwxr-xr-x</span> 2 khaled dev 4096 Sep 22 2025
						<span class="text-cyan-400">{category.toLowerCase()}/</span>
					</div>
					<div class="ml-8 space-y-1">
						{#each items as skill}
							<div
								class="group cursor-pointer rounded px-2 py-1 text-slate-400 transition-all hover:bg-slate-800/50 hover:text-slate-300"
							>
								<span class="text-green-400">-rw-r--r--</span>
								<span class="text-slate-400">1 khaled dev</span>
								<span class="rounded px-1 group-hover:bg-slate-700/50 group-hover:text-slate-200"
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
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-4 transition-all duration-300 hover:border-slate-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ which editor</div>
					<div class="text-slate-300">/usr/bin/cursor</div>
					<div class="mt-2 text-xs text-slate-400">Multitasking with Cursor [>_]</div>
				</div>
			</div>

			<div
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-4 transition-all duration-300 hover:border-slate-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ echo $SHELL</div>
					<div class="text-slate-300">/usr/bin/fish</div>
					<div class="mt-2 text-xs text-slate-400">Fish shell {'><(((°>'}</div>
				</div>
			</div>

			<div
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-4 transition-all duration-300 hover:border-slate-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ uname -r</div>
					<div class="text-slate-300">6.16.8-arch1-1</div>
					<div class="mt-2 text-xs text-slate-400">I use Arch BTW</div>
				</div>
			</div>

			<div
				class="rounded-lg border border-slate-700 bg-slate-900/50 p-4 transition-all duration-300 hover:border-slate-600"
			>
				<div class="text-sm">
					<div class="text-green-400">$ go version</div>
					<div class="text-slate-300">go version go1.21.0 linux/amd64</div>
					<div class="mt-2 text-xs text-slate-400">Gopher for life \o/</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Contact -->
	<section class="mx-auto space-y-6 border-t border-slate-800 pt-12">
		<code class="rounded border border-slate-700 bg-slate-900 px-3 py-1 text-green-400"
			>./get_in_touch.sh</code
		>

		<!-- Contact Info -->
		<div class="rounded-lg border border-slate-700 bg-black/60 p-6 text-sm">
			<div class="space-y-2">
				<div class="text-green-400">$ curl -s https://api.khaledwaleed.xyz/contact</div>
				<div class="text-slate-300">{'{'}</div>
				<div class="ml-4 text-slate-300">
					"status": "<span class="text-green-300">available</span>",
				</div>
				<div class="ml-4 text-slate-300">
					"email": "<a href="mailto:contact@khaledwaleed.xyz" class="text-cyan-400"
						>contact@khaledwaleed.xyz</a
					>",
				</div>
				<div class="ml-4 text-slate-300">
					"phone": "<a href="tel:+964783857755311" class="text-cyan-400">+964 783 8577 55311</a>",
				</div>
				<div class="ml-4 text-slate-300">
					"linkedin": "<a href="https://www.linkedin.com/in/kwaleedkhalid/" class="text-cyan-400"
						>linkedin.com/in/kwaleedkhalid/</a
					>",
				</div>
				<div class="ml-4 text-slate-300">
					"github": "<a href="https://github.com/61021" class="text-cyan-400">github.com/61021</a>",
				</div>
				<div class="ml-4 text-slate-300">
					"instagram": "<a href="https://www.instagram.com/khaled.jsx/" class="text-cyan-400"
						>instagram.com/khaled.jsx/</a
					>",
				</div>
				<div class="ml-4 text-slate-300">
					"telegram": "<a href="https://t.me/x61021" class="text-cyan-400">t.me/x61021</a>",
				</div>

				<div class="ml-4 text-slate-300">
					"whatsapp": "<a href="https://wa.me/message/6N52L7STPCUJO1" class="text-cyan-400"
						>wa.me/message/6N52L7STPCUJO1</a
					>",
				</div>

				<div class="text-slate-300">{'}'}</div>
				<div class="mt-4 text-green-400">$ echo "Let's build something great together"</div>
				<div class="text-slate-300">Let's build something great together</div>
			</div>
		</div>

		<!-- Contact Buttons -->
		<div class="flex flex-col justify-center gap-4 sm:flex-row">
			<a
				href="contact@khaledwaleed.xyz "
				class="inline-flex items-center justify-center rounded-md border border-slate-600 bg-slate-800 px-6 py-3 text-sm font-medium text-slate-200 shadow-lg transition-all duration-200 hover:bg-slate-700"
			>
				<span class="mr-2">$</span>
				echo "Hello" | mail khaled
			</a>
			<a
				href="/"
				class="inline-flex items-center justify-center rounded-md border border-slate-600 px-6 py-3 text-sm font-medium text-slate-300 transition-all duration-200 hover:bg-slate-800/50"
			>
				<span class="mr-2">$</span>
				cd ~
			</a>
		</div>

		<!-- Footer -->
		<div class="text-center text-sm text-slate-500">
			<div class="mt-8 rounded border border-slate-700 bg-slate-900/20 p-4">
				<span class="text-slate-400">"Code is poetry written for machines to understand."</span>
			</div>
		</div>
	</section>
</div>
