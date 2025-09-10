<script lang="ts">
	import '../app.css';
	import { writable } from 'svelte/store';

	let { children } = $props();

	// Track which dropdown is open
	const openMenu = writable<string>(''); 

	function toggleMenu(menu: string) {
		openMenu.update(current => current === menu ? '' : menu);
	}
</script>

<nav class="bg-white border-green-200 dark:bg-green-900 dark:border-green-700 sticky top-0 z-50 shadow-md">
	<div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
		<!-- Logo -->
		<a href="/" class="flex items-center space-x-3 rtl:space-x-reverse">
			<img src="../logo.jpg" class="h-8" alt="Logo" />
			<span class="self-center text-2xl font-bold whitespace-nowrap text-cyan-600 dark:text-cyan-400">
				SK GOMEZ
			</span>
		</a>

		<!-- Mobile Menu Button -->
		<button type="button"
			class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-green-500 rounded-lg md:hidden 
				   hover:bg-green-100 focus:outline-none focus:ring-2 focus:ring-cyan-500 dark:text-green-400 
				   dark:hover:bg-green-700 dark:focus:ring-cyan-400"
			aria-controls="navbar-dropdown" aria-expanded="false" aria-label="Open main menu">
			<svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none"
				viewBox="0 0 17 14">
				<path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
					d="M1 1h15M1 7h15M1 13h15" />
			</svg>
		</button>

		<!-- Desktop Nav -->
		<div class="hidden w-full md:block md:w-auto" id="navbar-dropdown">
			<ul
				class="flex flex-col font-medium p-4 md:p-0 mt-4 border border-green-100 rounded-lg bg-green-50 
				       md:space-x-8 rtl:space-x-reverse md:flex-row md:mt-0 md:border-0 
				       md:bg-white dark:bg-green-800 md:dark:bg-green-900 dark:border-green-700">

				<!-- Home -->
				<li>
					<a href="/" class="block py-2 px-3 text-white bg-cyan-600 rounded-lg md:bg-transparent 
						md:text-cyan-600 md:p-0 md:dark:text-cyan-400 hover:scale-105 transition-transform"
						aria-current="page">Home</a>
				</li>

				<!-- Reusable Dropdown Component -->
				{#each [
					{
						name: 'Barangay',
						key: 'barangay',
						links: [
							{ href: '/barangay/about', label: 'About' },
							{ href: '/barangay/chairperson', label: 'SK Chairperson' },
							{ href: '/barangay/councilors', label: 'SK Councilors' },
							{ href: '/barangay/committee', label: 'Committee' }
						]
					},
					{
						name: 'Programs',
						key: 'programs',
						links: [
							{ href: '/programs/education', label: 'Education' },
							{ href: '/programs/active-citizenship', label: 'Active Citizenship' },
							{ href: '/programs/health', label: 'Health and Sports' },
							{ href: '/programs/spiritual', label: 'Spiritual' },
							{ href: '/programs/environment', label: 'Environment' },
							{ href: '/programs/peace', label: 'Peace and Security' },
							{ href: '/programs/social', label: 'Social Inclusion and Equity' },
							{ href: '/programs/economic', label: 'Economic Empowerment' }
						]
					},
					{
						name: 'Services',
						key: 'services',
						links: [
							{ href: '/services/printing', label: 'Printing' },
							{ href: '/services/study-hub', label: 'Study Hub' }
						]
					},
					{
						name: 'Reports',
						key: 'reports',
						links: [
							{ href: '/reports/cbydp', label: 'CBYDP' },
							{ href: '/reports/annual', label: 'Annual Budget' },
							{ href: '/reports/monthly', label: 'Monthly Budget' }
						]
					}
				] as menu}
					<li class="relative">
						<button onclick={() => toggleMenu(menu.key)}
							class="flex items-center justify-between w-full py-2 px-3 text-green-900 rounded-sm 
							       hover:bg-green-100 md:hover:bg-transparent md:border-0 md:hover:text-cyan-600 
							       md:p-0 md:w-auto dark:text-white md:dark:hover:text-cyan-400 
							       dark:focus:text-white dark:border-green-700 dark:hover:bg-green-700 
							       md:dark:hover:bg-transparent">
							{menu.name}
							<svg class="w-2.5 h-2.5 ml-2 transition-transform duration-200"
								class:rotate-180={$openMenu === menu.key}
								aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
								<path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
									d="m1 1 4 4 4-4" />
							</svg>
						</button>
						{#if $openMenu === menu.key}
							<div class="absolute z-10 font-normal bg-white divide-y divide-green-100 rounded-lg shadow-md w-56 mt-2 dark:bg-green-700 dark:divide-green-600">
								<ul class="py-2 text-sm text-green-700 dark:text-green-400">
									{#each menu.links as link}
										<li>
											<a href={link.href}
												class="block px-4 py-2 hover:bg-cyan-50 hover:text-cyan-600 
												       dark:hover:bg-green-600 dark:hover:text-white">
												{link.label}
											</a>
										</li>
									{/each}
								</ul>
							</div>
						{/if}
					</li>
				{/each}
			</ul>
		</div>
	</div>
</nav>

<svelte:head>
	<title>SK Gomez - Barangay Gomez</title>
	<meta name="description" content="Official website of SK Gomez, Barangay Gomez." />
	<link rel="icon" href="../logo.jpg" />
</svelte:head>

<main class="max-w-screen-xl mx-auto px-4 py-6">
	{@render children()}
</main>

