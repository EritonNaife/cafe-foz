<script>
	import OpenNowBadge from '$lib/components/OpenNowBadge.svelte';
	import QuickInfoBar from '$lib/components/QuickInfoBar.svelte';
	import Reservation from '$lib/components/Reservation.svelte';

	const signatureItems = [
		{
			name: 'Pastel de Nata',
			description: 'Traditional Portuguese custard tart with caramelized top',
			price: '€2.50',
			image: 'https://images.unsplash.com/photo-1509440159596-0249088772ff?w=800&q=80'
		},
		{
			name: 'Croissant de Amêndoa',
			description: 'Almond croissant with house-made marzipan',
			price: '€3.80',
			image: 'https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=800&q=80'
		},
		{
			name: 'Açaí Bowl',
			description: 'Organic açaí with seasonal fruits and granola',
			price: '€8.50',
			image: 'https://images.unsplash.com/photo-1590301157890-4810ed352733?w=800&q=80'
		},
		{
			name: 'Coastal Brunch Plate',
			description: 'Smoked salmon, avocado toast, poached eggs',
			price: '€14.00',
			image: 'https://images.unsplash.com/photo-1525351484163-7529414344d8?w=800&q=80'
		}
	];

	const instagramImages = [
		'https://images.unsplash.com/photo-1559496417-e7f25c2f87c3?w=800&q=80',
		'https://images.unsplash.com/photo-1514066558159-fc8c737ef259?w=800&q=80',
		'https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=800&q=80',
		'https://images.unsplash.com/photo-1511920170033-f8396924c348?w=800&q=80',
		'https://images.unsplash.com/photo-1501443762994-82bd5dace89a?w=800&q=80',
		'https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=800&q=80'
	];
</script>

<svelte:head>
	<title>Maré - Coastal Bakery & Brunch in Foz do Douro</title>
</svelte:head>

<!-- Hero Section -->
<section class="relative mt-20 flex h-[85vh] min-h-[600px] items-center justify-center">
	<img
		src="https://images.unsplash.com/photo-1559925393-8be0ec4767c8?w=1920&q=80"
		alt="Coastal bakery interior with ocean view"
		class="absolute inset-0 h-full w-full object-cover"
	/>
	<div class="absolute inset-0 bg-gradient-to-b from-black/30 via-black/20 to-black/40" />

	<div class="relative z-10 mx-auto max-w-4xl px-4 text-center text-white">
		<div class="mb-6">
			<OpenNowBadge />
		</div>
		<h1 class="mb-6 font-heading text-5xl font-semibold tracking-tight md:text-7xl">
			Where Ocean Meets Pastry
		</h1>
		<p class="mx-auto mb-8 max-w-2xl font-body text-xl font-light text-white/95 md:text-2xl">
			Artisan bakery & coastal brunch in the heart of Foz do Douro
		</p>
	</div>
</section>

<!-- Quick Info Bar -->
<QuickInfoBar />

<!-- Signature Items -->
<section class="bg-background py-20">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="mb-16 text-center">
			<h2 class="mb-4 font-heading text-3xl font-semibold text-foreground md:text-5xl">
				Signature Selection
			</h2>
			<p class="mx-auto max-w-2xl font-body text-lg text-muted-foreground">
				Handcrafted daily with local ingredients and coastal inspiration
			</p>
		</div>

		<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
			{#each signatureItems as item, index}
				<div
					class="group shadow-coastal hover:shadow-coastal-lg overflow-hidden rounded-sm bg-card transition-all duration-300"
				>
					<div class="relative h-64 overflow-hidden">
						<img
							src={item.image}
							alt={item.name}
							class="absolute inset-0 h-full w-full object-cover transition-transform duration-500 group-hover:scale-105"
						/>
					</div>
					<div class="p-6">
						<div class="mb-2 flex items-start justify-between">
							<h3 class="font-heading text-xl font-semibold text-foreground">
								{item.name}
							</h3>
							<span class="font-body text-lg font-medium text-primary">
								{item.price}
							</span>
						</div>
						<p class="font-body text-sm leading-relaxed text-muted-foreground">
							{item.description}
						</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Reservation CTA -->
<Reservation />

<!-- Instagram Strip -->
<section class="bg-background py-20">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="mb-12 text-center">
			<h2 class="mb-4 font-heading text-3xl font-semibold text-foreground md:text-4xl">
				@mare.foz
			</h2>
			<p class="font-body text-lg text-muted-foreground">Follow our coastal journey</p>
		</div>

		<div class="grid grid-cols-2 gap-4 md:grid-cols-3 lg:grid-cols-6">
			{#each instagramImages as image, index}
				<div
					class="shadow-coastal hover:shadow-coastal-lg group relative aspect-square cursor-pointer overflow-hidden rounded-sm transition-all duration-300"
				>
					<img
						src={image}
						alt="Instagram post {index + 1}"
						class="absolute inset-0 h-full w-full object-cover transition-transform duration-500 group-hover:scale-110"
					/>
					<div
						class="absolute inset-0 bg-primary/0 transition-colors duration-300 group-hover:bg-primary/20"
					/>
				</div>
			{/each}
		</div>
	</div>
</section>
