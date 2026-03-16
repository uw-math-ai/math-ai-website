<section id="sponsors" class="section" style="position: relative; overflow: hidden;">
	<div class="container">
		<span class="badge badge-gold">Partners</span>
		<h2 class="section-title">Sponsors</h2>
		<p class="section-subtitle">
			This event is made possible through the generous support of our sponsors.
		</p>

		<div class="sponsors-showcase">
			<div class="sponsor-card glass-card">
				<div class="sponsor-logo">
					<span class="sponsor-icon">⬡</span>
				</div>
				<h3>Amazon Automated Reasoning Group</h3>
				<p>Supporting advances in formal verification and proof automation.</p>
				<span class="badge badge-gold">Title Sponsor</span>

				<!-- Decorative Lean snippet -->
				<div class="floating-snippet snippet-cta">
					<pre><code><span class="kw">def</span> <span class="fn">fibonacci</span> : ℕ → ℕ
  | 0     => 0
  | 1     => 1
  | n + 2 => <span class="fn">fibonacci</span> n + <span class="fn">fibonacci</span> (n + 1)</code></pre>
				</div>
			</div>
		</div>

		<div class="cta-section">
			<div class="cta-card glass-card glow-purple">
				<h2>Ready to Prove Something Amazing?</h2>
				<p>
					Apply to join us May 8–10, 2026 at the University of Washington for two days of hacking,
					learning, and collaboration around the Lean Proof Assistant.
					Spaces are limited — applications will be reviewed by the organizing committee.
				</p>
				<div class="cta-actions">
					<a href="https://docs.google.com/forms/d/14MZXvEmHV1iRMvncWguiUfyeDJbYOFKQVbbDYiSkf6A" class="btn btn-primary" target="_blank" rel="noopener">
						Apply to Participate →
					</a>
					<a href="https://docs.google.com/forms/d/1B0-I4yCrn4_Dbq9udhRTfFZIYdRP_kPwpoTtRjLVEvs" class="btn btn-outline" target="_blank" rel="noopener">
						RSVP as Invited Guest
					</a>
				</div>
			</div>
		</div>

	</div>
</section>

<style>
	.sponsors-showcase {
		display: flex;
		justify-content: center;
		margin-bottom: 5rem;
	}

	.sponsor-card {
		position: relative;
		overflow: visible;
		text-align: center;
		padding: 3rem 4rem;
		max-width: 500px;
		background: linear-gradient(135deg, rgba(232, 185, 49, 0.05), rgba(139, 84, 250, 0.05));
		border-color: rgba(232, 185, 49, 0.2);
	}

	.sponsor-card:hover {
		border-color: rgba(232, 185, 49, 0.4);
	}

	.sponsor-logo {
		margin-bottom: 1.5rem;
	}

	.sponsor-icon {
		font-size: 4rem;
		color: var(--gold-400);
	}

	.sponsor-card h3 {
		font-size: 1.3rem;
		color: var(--text-heading);
		margin-bottom: 0.75rem;
	}

	.sponsor-card p {
		color: var(--text-muted);
		font-size: 0.95rem;
		margin-bottom: 1.25rem;
		line-height: 1.6;
	}

	.cta-section {
		margin-top: 2rem;
	}

	.cta-card {
		text-align: center;
		padding: 4rem 3rem;
		background: linear-gradient(135deg, rgba(139, 84, 250, 0.12), rgba(107, 63, 160, 0.06));
		border-color: rgba(139, 84, 250, 0.3);
	}

	.cta-card h2 {
		font-size: 2.2rem;
		margin-bottom: 1rem;
		background: linear-gradient(135deg, var(--purple-300), var(--gold-400));
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	.cta-card p {
		color: var(--text-muted);
		font-size: 1.1rem;
		max-width: 600px;
		margin: 0 auto 2rem;
		line-height: 1.7;
	}

	.cta-actions {
		display: flex;
		gap: 1rem;
		justify-content: center;
		flex-wrap: wrap;
	}

	.floating-snippet {
		position: absolute;
		background: rgba(139, 84, 250, 0.06);
		border: 1px solid rgba(139, 84, 250, 0.15);
		border-radius: 12px;
		padding: 1rem 1.25rem;
		font-family: 'JetBrains Mono', monospace;
		font-size: 0.8rem;
		color: var(--text-muted);
		pointer-events: none;
		z-index: 0;
		white-space: pre;
		line-height: 1.6;
	}

	.floating-snippet pre {
		margin: 0;
	}

	.floating-snippet code {
		font-family: inherit;
	}

	.floating-snippet .kw { color: var(--purple-300); }
	.floating-snippet .fn { color: var(--gold-400); }

	.snippet-cta {
		top: -1.5rem;
		right: -12rem;
		transform: rotate(1.5deg);
		opacity: 0.45;
	}

	@media (max-width: 768px) {
		.sponsor-card {
			padding: 2rem;
		}
		.floating-snippet {
			display: none;
		}
		.cta-card {
			padding: 3rem 1.5rem;
		}
		.cta-card h2 {
			font-size: 1.7rem;
		}
	}
</style>
