<script lang="ts">
	let scrollY = $state(0);
	let visible = $state(false);

	$effect(() => {
		visible = true;
	});
</script>

<svelte:window bind:scrollY />

<nav class="navbar" class:scrolled={scrollY > 50}>
	<div class="nav-inner container">
		<a href="#top" class="nav-logo">
			<span class="logo-lean">∀</span>
			<span class="logo-text">UW Lean Hackathon</span>
		</a>
		<div class="nav-links">
			<a href="#about">About</a>
			<a href="#schedule">Schedule</a>
			<a href="#challenges">Challenges</a>
			<a href="#organizers">Organizers</a>
			<a href="#sponsors">Sponsors</a>
			<a href="https://docs.google.com/forms/d/14MZXvEmHV1iRMvncWguiUfyeDJbYOFKQVbbDYiSkf6A" class="btn btn-primary btn-nav" target="_blank" rel="noopener">
				Apply Now
			</a>
		</div>
	</div>
</nav>

<style>
	.navbar {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		z-index: 100;
		padding: 1rem 0;
		transition: all 0.3s ease;
	}

	.navbar.scrolled {
		background: rgba(13, 11, 20, 0.85);
		backdrop-filter: blur(20px);
		-webkit-backdrop-filter: blur(20px);
		border-bottom: 1px solid rgba(139, 84, 250, 0.1);
		padding: 0.6rem 0;
	}

	.nav-inner {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.nav-logo {
		display: flex;
		align-items: center;
		gap: 0.6rem;
		font-weight: 700;
		font-size: 1.1rem;
		color: white;
		text-decoration: none;
	}

	.logo-lean {
		font-family: var(--font-mono);
		font-size: 1.4rem;
		color: var(--purple-400);
	}

	.nav-links {
		display: flex;
		align-items: center;
		gap: 2rem;
	}

	.nav-links a {
		color: var(--text-muted);
		font-size: 0.9rem;
		font-weight: 500;
		transition: color 0.2s ease;
		text-decoration: none;
	}

	.nav-links a:hover {
		color: white;
	}

	.btn-nav {
		padding: 0.55rem 1.4rem;
		font-size: 0.85rem;
		color: white !important;
	}

	@media (max-width: 768px) {
		.nav-links a:not(.btn-nav) {
			display: none;
		}
	}
</style>
