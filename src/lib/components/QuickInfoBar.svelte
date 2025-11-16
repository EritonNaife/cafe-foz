<script>
	import { MapPin, Clock } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button/index.js';
</script>

<div class="border-y border-border bg-white py-6">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="grid grid-cols-1 items-center gap-6 md:grid-cols-3">
			<div class="flex items-start gap-3">
				<MapPin class="mt-0.5 h-5 w-5 flex-shrink-0 text-primary" />
				<div>
					<p class="font-body text-sm font-medium text-foreground">Avenida do Brasil 123</p>
					<p class="font-body text-sm text-muted-foreground">Foz do Douro, Porto</p>
				</div>
			</div>

			<div class="flex items-start gap-3">
				<Clock class="mt-0.5 h-5 w-5 flex-shrink-0 text-primary" />
				<div>
					<p class="font-body text-sm font-medium text-foreground">Tuesday - Sunday</p>
					<p class="font-body text-sm text-muted-foreground">8:00 AM - 8:00 PM</p>
				</div>
			</div>

			<div class="flex justify-start md:justify-end">
				<a
					href="/contact"
					class="inline-block rounded-sm bg-primary px-8 py-3 font-body text-sm tracking-wider text-primary-foreground uppercase transition-colors hover:bg-primary/90"
				>
					Reserve a Table
				</a>
			</div>
		</div>
	</div>
</div>
