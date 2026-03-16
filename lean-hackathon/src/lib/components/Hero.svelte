<script lang="ts">
	let visible = $state(false);

	$effect(() => {
		visible = true;
	});
</script>

<section id="top" class="hero">
	<!-- Animated background particles -->
	<div class="hero-bg">
		<div class="orb orb-1"></div>
		<div class="orb orb-2"></div>
		<div class="orb orb-3"></div>
		<div class="grid-overlay"></div>
	</div>

	<div class="hero-content container" class:visible>
		<div class="hero-badge">
			<span class="badge badge-purple">May 8–10, 2026</span>
			<span class="badge badge-gold">University of Washington</span>
		</div>

		<h1 class="hero-title">
			UW Lean<br />
			<span class="gradient-text">Hackathon</span>
			<span class="year">2026</span>
		</h1>

		<p class="hero-description">
			An invitation-only hackathon bringing together students, faculty, and industry partners
			to work on challenge problems showcasing the power of the
			<a href="https://lean-lang.org/" target="_blank" rel="noopener">Lean Proof Assistant</a>.
			A collaboration between the
			<a href="https://sites.math.washington.edu/ai/" target="_blank" rel="noopener">Math AI Lab</a>
			and the
			<a href="https://uwplse.org/" target="_blank" rel="noopener">PLSE Lab</a>
			at the University of Washington.
		</p>

		<div class="hero-actions">
			<a href="https://docs.google.com/forms/d/14MZXvEmHV1iRMvncWguiUfyeDJbYOFKQVbbDYiSkf6A" class="btn btn-primary" target="_blank" rel="noopener">
				Apply to Participate →
			</a>
			<a href="https://docs.google.com/forms/d/1B0-I4yCrn4_Dbq9udhRTfFZIYdRP_kPwpoTtRjLVEvs" class="btn btn-outline" target="_blank" rel="noopener">
				RSVP as Invited Guest
			</a>
		</div>

		<div class="hero-stats">
			<div class="stat">
				<span class="stat-number">2</span>
				<span class="stat-label">Days of Hacking</span>
			</div>
			<div class="stat-divider"></div>
			<div class="stat">
				<span class="stat-number">7+</span>
				<span class="stat-label">Challenge Tracks</span>
			</div>
			<div class="stat-divider"></div>
			<div class="stat">
				<span class="stat-number">∀</span>
				<span class="stat-label">Proofs Welcome</span>
			</div>
		</div>
	</div>

	<!-- Floating code snippet decoration -->
	<div class="floating-code" class:visible>
		<pre><code><span class="kw">theorem</span> <span class="fn">Nat.zero_add</span> : ∀ n, 0 + n = n
  | 0     => <span class="kw">rfl</span>
  | n + 1 => <span class="fn">congrArg</span> Nat.succ (<span class="fn">Nat.zero_add</span> n)</code></pre>
	</div>
</section>

<style>
	.hero {
		position: relative;
		min-height: 100vh;
		display: flex;
		align-items: center;
		overflow: hidden;
		padding-top: 5rem;
	}

	/* Animated background orbs */
	.hero-bg {
		position: absolute;
		inset: 0;
		z-index: 0;
	}

	.orb {
		position: absolute;
		border-radius: 50%;
		filter: blur(80px);
		opacity: 0.4;
		animation: float 20s ease-in-out infinite;
	}

	.orb-1 {
		width: 600px;
		height: 600px;
		background: radial-gradient(circle, rgba(139, 84, 250, 0.5), transparent);
		top: -10%;
		right: -10%;
		animation-delay: 0s;
	}

	.orb-2 {
		width: 400px;
		height: 400px;
		background: radial-gradient(circle, rgba(107, 63, 160, 0.4), transparent);
		bottom: -5%;
		left: -5%;
		animation-delay: -7s;
	}

	.orb-3 {
		width: 300px;
		height: 300px;
		background: radial-gradient(circle, rgba(232, 185, 49, 0.2), transparent);
		top: 40%;
		left: 50%;
		animation-delay: -14s;
	}

	.grid-overlay {
		position: absolute;
		inset: 0;
		background-image:
			linear-gradient(rgba(139, 84, 250, 0.03) 1px, transparent 1px),
			linear-gradient(90deg, rgba(139, 84, 250, 0.03) 1px, transparent 1px);
		background-size: 60px 60px;
	}

	@keyframes float {
		0%, 100% { transform: translate(0, 0) scale(1); }
		33% { transform: translate(30px, -30px) scale(1.05); }
		66% { transform: translate(-20px, 20px) scale(0.95); }
	}

	/* Hero content */
	.hero-content {
		position: relative;
		z-index: 1;
		opacity: 0;
		transform: translateY(30px);
		transition: all 1s cubic-bezier(0.16, 1, 0.3, 1);
	}

	.hero-content.visible {
		opacity: 1;
		transform: translateY(0);
	}

	.hero-badge {
		display: flex;
		gap: 0.75rem;
		margin-bottom: 2rem;
		flex-wrap: wrap;
	}

	.hero-title {
		font-size: clamp(3rem, 8vw, 6rem);
		font-weight: 900;
		line-height: 1.05;
		letter-spacing: -0.03em;
		margin-bottom: 1.5rem;
	}

	.gradient-text {
		background: linear-gradient(135deg, var(--purple-400), var(--purple-200), var(--gold-400));
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.year {
		font-family: var(--font-mono);
		font-size: 0.5em;
		color: var(--text-muted);
		vertical-align: super;
		margin-left: 0.3em;
	}

	.hero-description {
		font-size: 1.2rem;
		color: var(--text-muted);
		max-width: 550px;
		line-height: 1.7;
		margin-bottom: 2.5rem;
	}

	.hero-description a {
		color: var(--purple-300);
		text-decoration: underline;
		text-underline-offset: 3px;
	}

	.hero-actions {
		display: flex;
		gap: 1rem;
		margin-bottom: 4rem;
		flex-wrap: wrap;
	}

	.hero-stats {
		display: flex;
		align-items: center;
		gap: 2rem;
		flex-wrap: wrap;
	}

	.stat {
		display: flex;
		flex-direction: column;
	}

	.stat-number {
		font-size: 2rem;
		font-weight: 800;
		font-family: var(--font-mono);
		color: var(--purple-400);
	}

	.stat-label {
		font-size: 0.85rem;
		color: var(--text-muted);
	}

	.stat-divider {
		width: 1px;
		height: 40px;
		background: rgba(139, 84, 250, 0.3);
	}

	/* Floating code decoration */
	.floating-code {
		position: absolute;
		right: 6%;
		top: 14%;
		z-index: 1;
		background: rgba(20, 15, 35, 0.8);
		backdrop-filter: blur(20px);
		border: 1px solid rgba(139, 84, 250, 0.2);
		border-radius: 12px;
		padding: 1.5rem;
		font-family: var(--font-mono);
		font-size: 0.82rem;
		line-height: 1.6;
		opacity: 0;
		transform: translateY(20px) rotate(1.5deg);
		transition: all 1.2s cubic-bezier(0.16, 1, 0.3, 1) 0.5s;
		box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
	}

	.floating-code.visible {
		opacity: 1;
		transform: translateY(0) rotate(1.5deg);
	}

	.floating-code pre {
		margin: 0;
	}

	.floating-code .kw { color: var(--purple-300); }
	.floating-code .fn { color: var(--gold-400); }
	.floating-code .cm { color: var(--text-muted); }

	@media (max-width: 1024px) {
		.floating-code {
			display: none;
		}
	}

	@media (max-width: 768px) {
		.hero {
			padding-top: 6rem;
			min-height: auto;
			padding-bottom: 4rem;
		}
		.hero-stats {
			gap: 1.5rem;
		}
	}
</style>
