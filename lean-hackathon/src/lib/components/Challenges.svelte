<script lang="ts">
	const challenges = [
		{
			icon: '📐',
			title: 'Mathematical Formalization',
			description: 'Formalize a mathematical theorem or definition, possibly using available autoformalization tools. Contribute directly to Mathlib.',
			tags: ['Lean 4', 'Mathlib', 'Mathematics']
		},
		{
			icon: '🔐',
			title: 'Security Protocol Verification',
			description: 'Formalize a network security protocol in Lean, providing machine-checked guarantees about its correctness.',
			tags: ['Lean 4', 'Security', 'Verification']
		},
		{
			icon: '🤖',
			title: 'Autoformalization Model',
			description: 'Design a model targeting benchmarks like the AI Mathematical Olympiad progress prizes or SorryDB.',
			tags: ['LLMs', 'AI', 'Benchmarks']
		},
		{
			icon: '🎲',
			title: 'Probabilistic Programming',
			description: 'Formalize a probabilistic programming language in Lean, combining PL theory with formal verification.',
			tags: ['Lean 4', 'PL Theory', 'Probability']
		},
		{
			icon: '💬',
			title: 'Lean Sandbox for ChatGPT',
			description: 'Build a Lean sandbox server connected to ChatGPT, enabling AI-assisted interactive theorem proving.',
			tags: ['ChatGPT', 'Infrastructure', 'API']
		},
		{
			icon: '🧠',
			title: 'Neuro-Symbolic Conjectures',
			description: 'Auto-generate mathematical conjectures in Lean from informal text using neuro-symbolic AI techniques.',
			tags: ['Neural Networks', 'NLP', 'Lean 4']
		},
		{
			icon: '⚙️',
			title: 'Meta-Programming Tactics',
			description: 'Create or improve a Lean tactic — extend Lean\'s automation capabilities through meta-programming.',
			tags: ['Lean 4', 'Meta-programming', 'Tactics']
		}
	];
</script>

<section id="challenges" class="section" style="position: relative; overflow: hidden;">
	<div class="container">
		<span class="badge badge-purple">Get Inspired</span>
		<h2 class="section-title">Challenge Tracks</h2>
		<p class="section-subtitle">
			Teams will tackle one of these challenge areas. Each team will include at least one Lean-proficient researcher and one domain expert.
		</p>

		<div class="challenges-grid">
			{#each challenges as challenge, i}
				<div class="challenge-card glass-card" style="animation-delay: {i * 0.08}s">
					<div class="challenge-icon">{challenge.icon}</div>
					<h3>{challenge.title}</h3>
					<p>{challenge.description}</p>
					<div class="challenge-tags">
						{#each challenge.tags as tag}
							<span class="tag">{tag}</span>
						{/each}
					</div>
				</div>
			{/each}
		</div>

		<!-- Decorative Lean snippets -->
		<div class="floating-snippet snippet-left">
			<pre><code><span class="kw">theorem</span> <span class="fn">inf_primes</span> (n : ℕ) :
    ∃ p, n ≤ p ∧ Nat.Prime p :=
  <span class="fn">Nat.exists_infinite_primes</span> n</code></pre>
		</div>
		<div class="floating-snippet snippet-right">
			<pre><code><span class="kw">#check</span> @List.map
<span class="cm">-- {'{'}&alpha; &beta; : Type{'}'} &rarr;</span>
<span class="cm">--   (&alpha; &rarr; &beta;) &rarr; List &alpha; &rarr; List &beta;</span></code></pre>
		</div>
	</div>
</section>

<style>
	.challenges-grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
		gap: 1.5rem;
	}

	.challenge-card {
		animation: fadeInUp 0.6s ease both;
		display: flex;
		flex-direction: column;
	}

	.challenge-icon {
		font-size: 2.5rem;
		margin-bottom: 1rem;
	}

	.challenge-card h3 {
		font-size: 1.2rem;
		color: var(--text-heading);
		margin-bottom: 0.5rem;
	}

	.challenge-card p {
		color: var(--text-muted);
		font-size: 0.95rem;
		line-height: 1.6;
		flex: 1;
	}

	.challenge-tags {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
		margin-top: 1.25rem;
	}

	.tag {
		padding: 0.25rem 0.7rem;
		border-radius: 999px;
		font-size: 0.7rem;
		font-weight: 600;
		background: rgba(139, 84, 250, 0.1);
		color: var(--purple-300);
		border: 1px solid rgba(139, 84, 250, 0.2);
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

	@media (max-width: 768px) {
		.challenges-grid {
			grid-template-columns: 1fr;
		}
		.floating-snippet {
			display: none;
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
		opacity: 0.4;
	}

	.floating-snippet .kw { color: var(--purple-300); }
	.floating-snippet .fn { color: var(--gold-400); }
	.floating-snippet .cm { color: var(--text-muted); }

	.snippet-left {
		left: 2%;
		bottom: 6%;
		transform: rotate(-1.5deg);
	}

	.snippet-right {
		right: 2%;
		top: 8%;
		transform: rotate(1deg);
	}
</style>
