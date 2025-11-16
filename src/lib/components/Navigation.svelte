<script>
	import { page } from '$app/stores';
	import { Menu, X } from 'lucide-svelte';

	let isOpen = $state(false);

	const links = [
		{ href: '/', label: 'Home' },
		{ href: '/about', label: 'About' },
		{ href: '/contact', label: 'Contact' }
	];

	function isActive(href) {
		return $page.url.pathname === href;
	}

	function closeMenu() {
		isOpen = false;
	}
</script>

<nav
	class="shadow-coastal fixed top-0 right-0 left-0 z-50 border-b border-border bg-white/95 backdrop-blur-sm"
>
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-20 items-center justify-between">
			<!-- Logo -->
			<a href="/" class="flex items-center">
				<span class="font-heading text-2xl font-semibold tracking-wide text-primary sm:text-3xl">
					Maré
				</span>
			</a>

			<!-- Desktop Navigation -->
			<div class="hidden items-center space-x-8 md:flex">
				{#each links as link}
					<a
						href={link.href}
						class="font-body text-sm tracking-wider uppercase transition-colors {isActive(link.href)
							? 'font-medium text-primary'
							: 'text-foreground/70 hover:text-primary'}"
					>
						{link.label}
					</a>
				{/each}
				<a
					href="/contact"
					class="rounded-sm bg-primary px-6 py-2.5 font-body text-sm tracking-wider text-primary-foreground uppercase transition-colors hover:bg-primary/90"
				>
					Reserve
				</a>
			</div>

			<!-- Mobile Menu Button -->
			<button
				on:click={() => (isOpen = !isOpen)}
				class="p-2 text-foreground md:hidden"
				aria-label="Toggle menu"
			>
				{#if isOpen}
					<X size={24} />
				{:else}
					<Menu size={24} />
				{/if}
			</button>
		</div>

		<!-- Mobile Navigation -->
		{#if isOpen}
			<div class="border-t border-border py-6 md:hidden">
				<div class="flex flex-col space-y-4">
					{#each links as link}
						<a
							href={link.href}
							on:click={closeMenu}
							class="py-2 font-body text-sm tracking-wider uppercase transition-colors {isActive(
								link.href
							)
								? 'font-medium text-primary'
								: 'text-foreground/70'}"
						>
							{link.label}
						</a>
					{/each}
					<a
						href="/contact"
						on:click={closeMenu}
						class="rounded-sm bg-primary px-6 py-2.5 text-center font-body text-sm tracking-wider text-primary-foreground uppercase"
					>
						Reserve
					</a>
				</div>
			</div>
		{/if}
	</div>
</nav>
