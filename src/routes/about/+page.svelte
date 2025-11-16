<script lang="ts">
	import Reservation from '$lib/components/Reservation.svelte';

	const menuSections = [
		{
			title: 'Breakfast & Brunch',
			items: [
				{
					name: 'Avocado Toast Deluxe',
					description: 'Sourdough, smashed avocado, poached egg, cherry tomatoes',
					price: '€9.50',
					dietary: ['V', 'GF*']
				},
				{
					name: 'Açaí Power Bowl',
					description: 'Organic açaí, granola, fresh berries, coconut flakes',
					price: '€8.50',
					dietary: ['VG', 'GF']
				},
				{
					name: 'Coastal Benedict',
					description: 'English muffin, smoked salmon, poached eggs, hollandaise',
					price: '€13.00',
					dietary: []
				},
				{
					name: 'French Toast Stack',
					description: 'Brioche, caramelized banana, maple syrup, whipped cream',
					price: '€10.50',
					dietary: ['V']
				}
			]
		},
		{
			title: 'Bakery Selection',
			items: [
				{
					name: 'Pastel de Nata (Traditional)',
					description: 'Portuguese custard tart with cinnamon',
					price: '€2.50',
					dietary: ['V']
				},
				{
					name: 'Almond Croissant',
					description: 'Butter croissant, almond cream, toasted almonds',
					price: '€3.80',
					dietary: ['V']
				},
				{
					name: 'Pain au Chocolat',
					description: 'Flaky pastry with dark chocolate',
					price: '€3.20',
					dietary: ['V']
				},
				{
					name: 'Cinnamon Roll',
					description: 'House-made with cream cheese frosting',
					price: '€4.50',
					dietary: ['V']
				}
			]
		},
		{
			title: 'Beverages',
			items: [
				{
					name: 'Espresso / Americano',
					description: 'Single origin Portuguese roast',
					price: '€2.00 / €2.50',
					dietary: ['VG']
				},
				{
					name: 'Flat White / Cappuccino',
					description: 'With oat, almond, or dairy milk',
					price: '€3.50',
					dietary: ['V', 'VG*']
				},
				{
					name: 'Fresh Orange Juice',
					description: 'Squeezed daily from local oranges',
					price: '€4.00',
					dietary: ['VG', 'GF']
				},
				{
					name: 'Matcha Latte',
					description: 'Premium ceremonial grade matcha',
					price: '€4.50',
					dietary: ['V', 'VG*']
				}
			]
		}
	];

	const galleryImages = [
		{
			src: 'https://images.unsplash.com/photo-1551218808-94e220e084d2?w=1200&q=80',
			alt: 'Fresh pastries display'
		},
		{
			src: 'https://images.unsplash.com/photo-1511920170033-f8396924c348?w=1200&q=80',
			alt: 'Coffee brewing'
		},
		{
			src: 'https://images.unsplash.com/photo-1506619216599-9d16d0903dfd?w=1200&q=80',
			alt: 'Ocean view from terrace'
		},
		{
			src: 'https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=1200&q=80',
			alt: 'Coastal interior ambiance'
		},
		{
			src: 'https://images.unsplash.com/photo-1559056199-641a0ac8b55e?w=1200&q=80',
			alt: 'Brunch plate'
		},
		{
			src: 'https://images.unsplash.com/photo-1513639776629-7b61b0ac49cb?w=1200&q=80',
			alt: 'Fresh ingredients'
		}
	];
</script>

<main class="mt-20 min-h-screen">
	<!-- Hero Section -->
	<section class="relative flex h-[60vh] min-h-[500px] items-center justify-center">
		<img
			src="https://images.unsplash.com/photo-1554118811-1e0d58224f24?w=1920&q=80"
			alt="Maré interior and story"
			class="absolute inset-0 h-full w-full object-cover"
		/>

		<div class="absolute inset-0 bg-gradient-to-b from-black/40 via-black/30 to-black/50"></div>

		<div class="relative z-10 mx-auto max-w-4xl px-4 text-center text-white">
			<h1 class="mb-6 font-heading text-5xl font-semibold md:text-6xl">Our Story</h1>
			<p class="font-body text-xl font-light text-white/95 md:text-2xl">
				Celebrating Portuguese tradition with coastal elegance
			</p>
		</div>
	</section>

	<!-- Story Section -->
	<section class="bg-background py-20">
		<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8">
			<div class="grid grid-cols-1 items-center gap-12 md:grid-cols-2">
				<div>
					<h2 class="mb-6 font-heading text-3xl font-semibold text-foreground md:text-4xl">
						Born by the Atlantic
					</h2>

					<div class="space-y-4 font-body leading-relaxed text-muted-foreground">
						<p>
							Maré was founded in 2019 by chef Ana Silva and pastry artisan João Costa, both Porto
							natives with a deep love for their coastal homeland. Inspired by the rhythm of the
							Atlantic tides and the warmth of Portuguese hospitality, they set out to create a
							space where tradition meets contemporary elegance.
						</p>
						<p>
							Our name, "Maré" (tide), reflects our philosophy: fresh, seasonal ingredients that
							flow with nature's rhythm. Every morning, we bake pastries using century-old
							techniques, source produce from local farmers, and brew coffee that honors Portugal's
							rich culinary heritage.
						</p>
						<p>
							Nestled in Foz do Douro's most picturesque corner, our bakery offers more than just
							food—it's a lifestyle. Whether you're savoring a pastel de nata with your morning
							espresso or enjoying weekend brunch with ocean views, Maré is your coastal escape.
						</p>
					</div>
				</div>

				<div class="shadow-coastal-lg relative h-[500px] overflow-hidden rounded-sm">
					<img
						src="https://images.unsplash.com/photo-1556742393-d75f468bfcb0?w=800&q=80"
						alt="Chef preparing pastries"
						class="absolute inset-0 h-full w-full object-cover"
					/>
				</div>
			</div>
		</div>
	</section>

	<!-- Menu Section -->
	<section class="bg-primary/5 py-20">
		<div class="mx-auto max-w-6xl px-4 sm:px-6 lg:px-8">
			<div class="mb-16 text-center">
				<h2 class="mb-4 font-heading text-3xl font-semibold text-foreground md:text-5xl">Menu</h2>
				<p class="mb-6 font-body text-lg text-muted-foreground">
					Crafted daily with passion and Portuguese pride
				</p>

				<div class="flex flex-wrap justify-center gap-4 font-body text-sm">
					<span class="inline-flex items-center gap-2">
						<span class="font-semibold">V</span> Vegetarian
					</span>
					<span class="inline-flex items-center gap-2">
						<span class="font-semibold">VG</span> Vegan
					</span>
					<span class="inline-flex items-center gap-2">
						<span class="font-semibold">GF</span> Gluten-Free
					</span>
					<span class="inline-flex items-center gap-2">
						<span class="font-semibold">*</span> Available on request
					</span>
				</div>
			</div>

			<div class="space-y-16">
				{#each menuSections as section}
					<div>
						<h3
							class="mb-8 text-center font-heading text-2xl font-semibold text-foreground md:text-3xl"
						>
							{section.title}
						</h3>

						<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
							{#each section.items as item}
								<div
									class="shadow-coastal hover:shadow-coastal-lg rounded-sm bg-card p-6 transition-all duration-300"
								>
									<div class="mb-2 flex items-start justify-between">
										<h4 class="flex-1 font-heading text-lg font-semibold text-foreground">
											{item.name}
										</h4>
										<span class="ml-4 font-body text-lg font-medium text-primary">{item.price}</span
										>
									</div>

									<p class="mb-3 font-body text-sm leading-relaxed text-muted-foreground">
										{item.description}
									</p>

									{#if item.dietary.length > 0}
										<div class="flex gap-2">
											{#each item.dietary as label}
												<span
													class="rounded bg-primary/10 px-2 py-1 font-body text-xs font-semibold text-primary"
												>
													{label}
												</span>
											{/each}
										</div>
									{/if}
								</div>
							{/each}
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Gallery Section -->
	<section class="bg-background py-20">
		<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
			<div class="mb-16 text-center">
				<h2 class="mb-4 font-heading text-3xl font-semibold text-foreground md:text-5xl">
					Gallery
				</h2>
				<p class="font-body text-lg text-muted-foreground">Moments from our coastal kitchen</p>
			</div>

			<div class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
				{#each galleryImages as image}
					<div
						class="shadow-coastal hover:shadow-coastal-lg group relative aspect-[4/3]
                      cursor-pointer overflow-hidden rounded-sm transition-all duration-300"
					>
						<img
							src={image.src}
							alt={image.alt}
							class="absolute inset-0 h-full w-full object-cover transition-transform duration-500 group-hover:scale-105"
						/>

						<div
							class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0
                        transition-opacity duration-300 group-hover:opacity-100"
						></div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Reservation CTA -->
	<Reservation />
</main>
