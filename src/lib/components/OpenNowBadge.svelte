<script>
	import { onMount, onDestroy } from 'svelte';

	let isOpen = $state(false);
	let interval;

	function checkIfOpen() {
		const now = new Date();
		const hours = now.getHours();
		const day = now.getDay();

		// Open 8am-8pm, Tuesday-Sunday (closed Monday)
		isOpen = day !== 1 && hours >= 8 && hours < 20;
	}

	onMount(() => {
		checkIfOpen();
		interval = setInterval(checkIfOpen, 60000); // Check every minute
	});

	onDestroy(() => {
		if (interval) {
			clearInterval(interval);
		}
	});
</script>

<div
	class="shadow-coastal inline-flex items-center gap-2 rounded-full bg-white/90 px-4 py-2 backdrop-blur-sm"
>
	<div class="h-2 w-2 rounded-full {isOpen ? 'animate-pulse bg-green-500' : 'bg-red-400'}" />
	<span class="font-body text-sm font-medium text-foreground">
		{isOpen ? 'Open Now' : 'Closed'}
	</span>
</div>
