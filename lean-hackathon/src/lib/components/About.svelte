<script lang="ts">
	const goals = [
		{
			icon: '🧮',
			title: 'Formalize Mathematics',
			description: 'Formalize mathematical statements and their proofs in Lean with the goal of contributing to Mathlib.'
		},
		{
			icon: '🛠️',
			title: 'Build Infrastructure',
			description: 'Create and improve infrastructure and tools that assist the formalization process.'
		},
		{
			icon: '🤝',
			title: 'Cross-Disciplinary Collaboration',
			description: 'Foster collaboration across PL, verification, LLMs, and mathematics communities.'
		},
		{
			icon: '🌍',
			title: 'Expand the Community',
			description: 'Introduce Lean to a wider audience and grow the ecosystem of contributors and users.'
		},
		{
			icon: '🏢',
			title: 'Industry Partnerships',
			description: 'Build and deepen connections between academia and industry around formal verification.'
		},
		{
			icon: '🏆',
			title: 'Ambitious Problems',
			description: 'Tackle ambitious cross-disciplinary challenge problems that push the boundaries of what\'s possible.'
		}
	];
</script>

<section id="about" class="section" style="position: relative; overflow: hidden;">
	<div class="container">
		<span class="badge badge-purple">About the Event</span>
		<h2 class="section-title">Why Lean Hackathon?</h2>
		<p class="section-subtitle">
			An invitation-only event at the intersection of mathematics, programming languages, and AI — hosted at the University of Washington. Apply and our organizers will review your application.
		</p>

		<div class="goals-grid">
			{#each goals as goal, i}
				<div class="glass-card goal-card" style="animation-delay: {i * 0.1}s">
					<span class="goal-icon">{goal.icon}</span>
					<h3>{goal.title}</h3>
					<p>{goal.description}</p>
				</div>
			{/each}
		</div>

		<!-- Decorative Lean snippet -->
		<div class="floating-snippet snippet-right">
			<pre><code><span class="kw">import</span> Mathlib.Data.Nat.Prime.Basic

<span class="kw">#check</span> <span class="fn">Nat.Prime</span>
<span class="cm">-- ℕ → Prop</span></code></pre>
		</div>

	</div>
</section>

<style>
	.goals-grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
		gap: 1.5rem;
		margin-bottom: 3rem;
	}

	.goal-card {
		animation: fadeInUp 0.6s ease both;
	}

	.goal-icon {
		font-size: 2.5rem;
		display: block;
		margin-bottom: 1rem;
	}

	.goal-card h3 {
		font-size: 1.2rem;
		margin-bottom: 0.5rem;
		color: var(--text-heading);
	}

	.goal-card p {
		color: var(--text-muted);
		font-size: 0.95rem;
		line-height: 1.6;
	}

	@keyframes fadeInUp {
		from {
			opacity: 0;
			transform: translateY(20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.floating-snippet {
		position: absolute;
		background: rgba(20, 15, 35, 0.7);
		backdrop-filter: blur(16px);
		border: 1px solid rgba(139, 84, 250, 0.15);
		border-radius: 10px;
		padding: 1rem 1.25rem;
		font-family: var(--font-mono);
		font-size: 0.75rem;
		line-height: 1.5;
		color: var(--text);
		pointer-events: none;
		z-index: 0;
		opacity: 0.5;
	}

	.floating-snippet .kw { color: var(--purple-300); }
	.floating-snippet .fn { color: var(--gold-400); }
	.floating-snippet .cm { color: var(--text-muted); }

	.snippet-right {
		right: 3%;
		top: 8%;
		transform: rotate(1.5deg);
	}

	@media (max-width: 768px) {
		.goals-grid {
			grid-template-columns: 1fr;
		}
		.floating-snippet {
			display: none;
		}
	}
</style>
