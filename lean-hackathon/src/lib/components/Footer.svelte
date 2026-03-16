<footer class="footer">
	<div class="container">
		<div class="footer-inner">
			<div class="footer-brand">
				<span class="footer-logo">∀</span>
				<span>UW Lean Hackathon 2026</span>
			</div>
			<div class="footer-links">
				<a href="https://lean-lang.org/" target="_blank" rel="noopener">Lean 4</a>
				<a href="https://leanprover-community.github.io/" target="_blank" rel="noopener">Mathlib</a>
				<a href="https://sites.math.washington.edu/ai/" target="_blank" rel="noopener">Math AI Lab</a>
				<a href="https://uwplse.org/" target="_blank" rel="noopener">PLSE Lab</a>
			</div>
			<p class="footer-copy">
				Department of Mathematics, University of Washington © 2026
			</p>
		</div>
	</div>
</footer>

<style>
	.footer {
		border-top: 1px solid rgba(139, 84, 250, 0.1);
		padding: 3rem 0;
		margin-top: 2rem;
	}

	.footer-inner {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1.5rem;
		text-align: center;
	}

	.footer-brand {
		display: flex;
		align-items: center;
		gap: 0.75rem;
		font-weight: 700;
		font-size: 1.1rem;
		color: var(--text-heading);
	}

	.footer-logo {
		font-family: var(--font-mono);
		font-size: 1.4rem;
		color: var(--purple-400);
	}

	.footer-links {
		display: flex;
		gap: 2rem;
		flex-wrap: wrap;
		justify-content: center;
	}

	.footer-links a {
		color: var(--text-muted);
		font-size: 0.9rem;
		transition: color 0.2s ease;
	}

	.footer-links a:hover {
		color: var(--purple-300);
	}

	.footer-copy {
		color: var(--text-muted);
		font-size: 0.8rem;
		opacity: 0.7;
	}
</style>
