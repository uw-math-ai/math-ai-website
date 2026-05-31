<script lang="ts">
	import { browser } from '$app/environment';

	let { children, class: className = '' } = $props();
	let element: HTMLElement;
	let visible = $state(false);

	$effect(() => {
		if (!browser || !element) return;
		if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
			visible = true;
			return;
		}

		const observer = new IntersectionObserver(
			(entries) => {
				if (entries[0].isIntersecting) {
					visible = true;
					observer.disconnect();
				}
			},
			{ threshold: 0.12 }
		);

		observer.observe(element);
		return () => observer.disconnect();
	});
</script>

<div bind:this={element} class={`reveal ${className}`} class:visible>
	{@render children()}
</div>

<style>
	.reveal {
		opacity: 0;
		transform: translateY(18px);
		transition:
			opacity 520ms ease,
			transform 520ms ease;
	}

	.reveal.visible {
		opacity: 1;
		transform: translateY(0);
	}

	@media (prefers-reduced-motion: reduce) {
		.reveal {
			opacity: 1;
			transform: none;
			transition: none;
		}
	}
</style>
