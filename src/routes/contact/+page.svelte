<script>
	import { MapPin, Phone, Mail, Clock } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Textarea } from '$lib/components/ui/textarea/index.js';

	let formData = $state({
		name: '',
		email: '',
		phone: '',
		date: '',
		guests: '',
		message: ''
	});

	let submitted = $state(false);

	function handleSubmit(e) {
		e.preventDefault();
		// In a real app, this would send to an API
		submitted = true;
		setTimeout(() => {
			submitted = false;
		}, 5000);
	}

	const faqs = [
		{
			question: 'Do you take reservations?',
			answer:
				'Yes! We recommend reserving for weekend brunch and dinner service. Walk-ins are welcome subject to availability.'
		},
		{
			question: 'Do you accommodate dietary restrictions?',
			answer:
				'Absolutely. We offer vegetarian, vegan, and gluten-free options. Please inform us of any allergies when booking.'
		},
		{
			question: 'Is there parking available?',
			answer:
				"Street parking is available nearby. We're also easily accessible by Porto's public transport system."
		},
		{
			question: 'Can I host a private event?',
			answer:
				'Yes! We offer private dining for groups of 15-40 guests. Contact us for more information.'
		}
	];
</script>

<svelte:head>
	<title>Contact & Reservations - Maré</title>
</svelte:head>

<!-- Hero CTA -->
<section class="mt-20 bg-gradient-to-br from-primary/10 to-secondary/20 py-20 text-center">
	<div class="mx-auto max-w-4xl px-4 sm:px-6 lg:px-8">
		<h1 class="mb-6 font-heading text-4xl font-semibold text-foreground md:text-6xl">Visit Us</h1>
		<p class="mx-auto mb-8 max-w-2xl font-body text-xl text-muted-foreground">
			Reserve your table and experience the finest coastal dining in Foz do Douro. We can't wait to
			welcome you.
		</p>
	</div>
</section>

<section class="bg-background py-20">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 md:px-8">
		<div class="grid grid-cols-1 gap-12 md:grid-cols-2">
			<div class="shadow-coastal rounded-sm bg-card p-8">
				<h2 class="mb-6 font-heading text-3xl font-semibold text-foreground">Make a Reservation</h2>

				{#if submitted}
					<div class="mb-6 rounded-sm border border-green-200 bg-green-50 p-4">
						<p class="font-body text-sm text-green-800">
							Thank you! We've received your reservation request and will confirm via email shortly.
						</p>
					</div>
				{/if}

				<form on:submit={handleSubmit} class="space-y-6">
					<div class="grid grid-cols-1 gap-4 sm:grid-cols-2">
						<div>
							<label for="name" class="mb-2 block font-body text-sm font-medium text-foreground">
								Name *
							</label>
							<Input
								id="name"
								name="name"
								type="text"
								required
								bind:value={formData.name}
								class="font-body"
							/>
						</div>
						<div>
							<label for="email" class="mb-2 block font-body text-sm font-medium text-foreground">
								Email *
							</label>
							<Input
								id="email"
								name="email"
								type="email"
								required
								bind:value={formData.email}
								class="font-body"
							/>
						</div>
					</div>

					<div class="grid grid-cols-1 gap-4 sm:grid-cols-2">
						<div>
							<label for="phone" class="mb-2 block font-body text-sm font-medium text-foreground">
								Phone
							</label>
							<Input
								id="phone"
								name="phone"
								type="tel"
								bind:value={formData.phone}
								class="font-body"
							/>
						</div>
						<div>
							<label for="guests" class="mb-2 block font-body text-sm font-medium text-foreground">
								Number of Guests *
							</label>
							<Input
								id="guests"
								name="guests"
								type="number"
								min="1"
								max="20"
								required
								bind:value={formData.guests}
								class="font-body"
							/>
						</div>
					</div>

					<div>
						<label for="date" class="mb-2 block font-body text-sm font-medium text-foreground">
							Preferred Date & Time *
						</label>
						<Input
							id="date"
							name="date"
							type="datetime-local"
							required
							bind:value={formData.date}
							class="font-body"
						/>
					</div>

					<div>
						<label for="message" class="mb-2 block font-body text-sm font-medium text-foreground">
							Special Requests
						</label>
						<Textarea
							id="message"
							name="message"
							rows={4}
							bind:value={formData.message}
							placeholder="Dietary restrictions, occasion, seating preferences..."
							class="font-body"
						/>
					</div>

					<Button type="submit" class="w-full py-6 font-body text-base tracking-wider uppercase">
						Submit Reservation
					</Button>
				</form>
			</div>

			<div class="space-y-8">
				<div class="shadow-coastal rounded-sm bg-card p-8">
					<h3 class="mb-6 font-heading text-2xl font-semibold text-foreground">
						Contact Information
					</h3>
					<div class="space-y-6">
						<div class="flex items-start gap-4">
							<MapPin class="mt-1 h-5 w-5 flex-shrink-0 text-primary" />
							<div>
								<p class="font-body font-medium text-foreground">Avenida do Brasil 123</p>
								<p class="font-body text-muted-foreground">4150-154 Foz do Douro, Porto</p>
							</div>
						</div>

						<div class="flex items-start gap-4">
							<Phone class="mt-1 h-5 w-5 flex-shrink-0 text-primary" />
							<div>
								<p class="font-body font-medium text-foreground">+351 22 123 4567</p>
								<p class="font-body text-sm text-muted-foreground">
									Available during business hours
								</p>
							</div>
						</div>

						<div class="flex items-start gap-4">
							<Mail class="mt-1 h-5 w-5 flex-shrink-0 text-primary" />
							<div>
								<p class="font-body font-medium text-foreground">hello@marefoz.pt</p>
								<p class="font-body text-sm text-muted-foreground">We'll respond within 24 hours</p>
							</div>
						</div>

						<div class="flex items-start gap-4">
							<Clock class="mt-1 h-5 w-5 flex-shrink-0 text-primary" />
							<div>
								<p class="font-body font-medium text-foreground">Tuesday - Sunday</p>
								<p class="font-body text-muted-foreground">8:00 AM - 8:00 PM</p>
								<p class="mt-1 font-body text-sm text-muted-foreground">Closed Mondays</p>
							</div>
						</div>
					</div>
				</div>

				<div class="shadow-coastal overflow-hidden rounded-sm bg-card">
					<div class="relative h-[400px] bg-muted">
						<iframe
							src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3004.3156889374344!2d-8.6767!3d41.1496!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zNDHCsDA4JzU4LjYiTiA4wrA0MCczNi4xIlc!5e0!3m2!1sen!2spt!4v1234567890"
							width="100%"
							height="100%"
							style={{ border: 0 }}
							allowFullScreen
							loading="lazy"
							referrerPolicy="no-referrer-when-downgrade"
							title="Maré location map"
						/>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- FAQ Section -->
<section class="bg-primary/5 py-20">
	<div class="mx-auto max-w-4xl px-4 sm:px-6 lg:px-8">
		<div class="mb-12 text-center">
			<h2 class="mb-4 font-heading text-3xl font-semibold text-foreground md:text-4xl">
				Frequently Asked Questions
			</h2>
		</div>

		<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
			{#each faqs as faq}
				<div class="shadow-coastal rounded-sm bg-card p-6">
					<h3 class="mb-3 font-heading text-lg font-semibold text-foreground">
						{faq.question}
					</h3>
					<p class="font-body leading-relaxed text-muted-foreground">
						{faq.answer}
					</p>
				</div>
			{/each}
		</div>
	</div>
</section>
