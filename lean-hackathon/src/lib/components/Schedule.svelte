<script lang="ts">
	interface ScheduleEvent {
		time: string;
		title: string;
		speaker?: string;
		description?: string;
		abstract?: string;
		venue: string;
		type: 'talk' | 'hack' | 'food' | 'social' | 'ceremony';
	}

	interface ScheduleDay {
		date: string;
		label: string;
		events: ScheduleEvent[];
	}

	const schedule: ScheduleDay[] = [
		{
			date: 'May 1 (Thu)',
			label: 'Pre-Event',
			events: [
				{
					time: '4:30 – 6:00 PM',
					title: 'Meet Your Teammates & Setup',
					description: 'Meet your teammates, get briefed on your challenge problem, and set up a common Lean environment. Info will also be shared with external participants.',
					venue: 'TBD',
					type: 'social'
				}
			]
		},
		{
			date: 'May 8 (Fri)',
			label: 'Colloquium & Reception',
			events: [
				{
					time: '3:30 – 4:30 PM',
					title: 'Lean: Machine-Checked Mathematics and AI Collaboration',
					speaker: 'Leonardo de Moura, creator of Lean',
					abstract: 'Lean is a proof assistant and programming language designed to make formal verification practical. In this talk, Leo will describe how Lean works, what it can do today, and where it is going. The core idea is simple: every mathematical claim and every program can be checked by a machine. This changes what collaboration looks like — between mathematicians, between engineers, and increasingly between humans and AI systems. The talk will cover recent work on proof automation and AI-assisted formalization, including experiments where multi-agent AI systems work autonomously on Lean tasks, as well as the Lean FRO, a nonprofit building Lean as long-term open infrastructure for mathematics and verified software.',
					venue: 'TBD',
					type: 'talk'
				},
				{
					time: '4:30 – 6:00 PM',
					title: 'Invitation-Only Reception',
					description: 'Reception for hackathon participants along with faculty from Mathematics, Computer Science, and ECE.',
					venue: 'TBD',
					type: 'social'
				}
			]
		},
		{
			date: 'May 9 (Sat)',
			label: 'Hacking Day 1',
			events: [
				{ time: '9:00 AM', title: 'Registration, Bagels & Coffee', venue: 'TBD', type: 'food' },
				{ time: '10:00 – 10:30 AM', title: 'Problem Overview', description: 'Presentation of all challenge tracks.', venue: 'TBD', type: 'talk' },
				{ time: '10:30 AM – 12:00 PM', title: 'Hacking Session 1', venue: 'TBD', type: 'hack' },
				{ time: '12:00 – 1:30 PM', title: 'Catered Lunch', venue: 'TBD', type: 'food' },
				{ time: '1:30 – 5:30 PM', title: 'Hacking Session 2', venue: 'TBD', type: 'hack' },
				{ time: '5:30 PM', title: 'Catered Dinner', description: 'Dinner to encourage folks to stay late and keep hacking!', venue: 'TBD', type: 'food' },
				{ time: 'Evening', title: 'Late Night Hacking', description: 'Room will be available for those who want to continue.', venue: 'TBD', type: 'hack' }
			]
		},
		{
			date: 'May 10 (Sun)',
			label: 'Hacking Day 2',
			events: [
				{ time: '9:00 AM', title: 'Coffee & Bagels', venue: 'TBD', type: 'food' },
				{ time: '9:30 AM – 12:00 PM', title: 'Hacking Session 3', venue: 'TBD', type: 'hack' },
				{ time: '12:00 – 1:00 PM', title: 'Catered Lunch', venue: 'TBD', type: 'food' },
				{ time: '1:00 – 3:00 PM', title: 'Final Hacking Sprint', venue: 'TBD', type: 'hack' },
				{ time: '4:00 PM', title: '🏆 Prizes & Presentations', description: 'Teams present their work. Prizes awarded.', venue: 'TBD', type: 'ceremony' }
			]
		}
	];

	let activeDay = $state(2);

	const typeColors: Record<string, string> = {
		talk: '#a87cff',
		hack: '#8b54fa',
		food: '#f0cc5b',
		social: '#c9aaff',
		ceremony: '#e8b931'
	};

	const typeLabels: Record<string, string> = {
		talk: '🎤 Talk',
		hack: '💻 Hack',
		food: '🍕 Food',
		social: '🤝 Social',
		ceremony: '🏆 Ceremony'
	};
</script>

<section id="schedule" class="section">
	<div class="container">
		<span class="badge badge-purple">Plan Ahead</span>
		<h2 class="section-title">Schedule</h2>
		<p class="section-subtitle">Four days of talks, hacking, and collaboration.</p>

		<div class="day-tabs">
			{#each schedule as day, i}
				<button
					class="day-tab"
					class:active={activeDay === i}
					onclick={() => (activeDay = i)}
				>
					<span class="day-tab-date">{day.date}</span>
					<span class="day-tab-label">{day.label}</span>
				</button>
			{/each}
		</div>

		{#key activeDay}
			<div class="timeline">
				{#each schedule[activeDay].events as event, i}
					<div class="timeline-item" style="animation-delay: {i * 0.08}s">
						<div class="timeline-marker" style="background: {typeColors[event.type]}"></div>
						<div class="timeline-content glass-card">
							<div class="timeline-header">
								<span class="timeline-time">{event.time}</span>
								<span class="timeline-type" style="color: {typeColors[event.type]}">{typeLabels[event.type]}</span>
							</div>
							<h3>{event.title}</h3>
						{#if event.speaker}
							<p class="timeline-speaker">{event.speaker}</p>
						{/if}
						<span class="timeline-venue">📍 {event.venue}</span>
						{#if event.description}
							<p>{event.description}</p>
						{/if}
						{#if event.abstract}
							<div class="timeline-abstract">
								<span class="abstract-label">Abstract</span>
								<p>{event.abstract}</p>
							</div>
							{/if}
						</div>
					</div>
				{/each}
			</div>
		{/key}
	</div>
</section>

<style>
	.day-tabs {
		display: flex;
		gap: 0.75rem;
		margin-bottom: 3rem;
		flex-wrap: wrap;
	}

	.day-tab {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		padding: 1rem 1.5rem;
		border-radius: 12px;
		border: 1px solid rgba(139, 84, 250, 0.15);
		background: rgba(30, 22, 50, 0.5);
		cursor: pointer;
		transition: all 0.3s ease;
		color: var(--text-muted);
		min-width: 160px;
	}

	.day-tab:hover {
		border-color: rgba(139, 84, 250, 0.4);
		background: rgba(139, 84, 250, 0.08);
	}

	.day-tab.active {
		border-color: var(--purple-400);
		background: rgba(139, 84, 250, 0.15);
		color: white;
		box-shadow: 0 4px 20px rgba(139, 84, 250, 0.2);
	}

	.day-tab-date {
		font-size: 0.8rem;
		font-weight: 600;
		opacity: 0.8;
	}

	.day-tab-label {
		font-size: 1rem;
		font-weight: 700;
	}

	.timeline {
		position: relative;
		padding-left: 2rem;
	}

	.timeline::before {
		content: '';
		position: absolute;
		left: 6px;
		top: 0;
		bottom: 0;
		width: 2px;
		background: linear-gradient(to bottom, var(--purple-400), transparent);
	}

	.timeline-item {
		position: relative;
		margin-bottom: 1.25rem;
		animation: fadeInLeft 0.5s ease both;
	}

	.timeline-marker {
		position: absolute;
		left: -2rem;
		top: 1.5rem;
		width: 14px;
		height: 14px;
		border-radius: 50%;
		transform: translateX(-3px);
		box-shadow: 0 0 12px rgba(139, 84, 250, 0.4);
	}

	.timeline-content {
		padding: 1.25rem 1.5rem;
	}

	.timeline-content:hover {
		transform: translateY(-2px);
	}

	.timeline-header {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 0.5rem;
		flex-wrap: wrap;
		gap: 0.5rem;
	}

	.timeline-time {
		font-family: var(--font-mono);
		font-size: 0.85rem;
		color: var(--purple-300);
		font-weight: 500;
	}

	.timeline-type {
		font-size: 0.75rem;
		font-weight: 600;
	}

	.timeline-content h3 {
		font-size: 1.1rem;
		color: var(--text-heading);
		margin-bottom: 0.3rem;
	}

	.timeline-venue {
		display: inline-block;
		font-size: 0.78rem;
		color: var(--text-muted);
		margin-bottom: 0.4rem;
		opacity: 0.8;
	}

	.timeline-content p {
		color: var(--text-muted);
		font-size: 0.9rem;
		line-height: 1.5;
	}

	.timeline-speaker {
		font-size: 0.9rem;
		color: var(--gold-400);
		font-weight: 500;
		margin-bottom: 0.3rem;
	}

	.timeline-abstract {
		margin-top: 0.75rem;
		padding-top: 0.75rem;
		border-top: 1px solid rgba(139, 84, 250, 0.1);
	}

	.abstract-label {
		display: inline-block;
		font-size: 0.7rem;
		font-weight: 700;
		text-transform: uppercase;
		letter-spacing: 0.08em;
		color: var(--purple-300);
		margin-bottom: 0.4rem;
	}

	.timeline-abstract p {
		font-size: 0.85rem;
		line-height: 1.6;
		color: var(--text-muted);
		opacity: 0.85;
	}

	@keyframes fadeInLeft {
		from {
			opacity: 0;
			transform: translateX(-20px);
		}
		to {
			opacity: 1;
			transform: translateX(0);
		}
	}

	@media (max-width: 768px) {
		.day-tabs {
			gap: 0.5rem;
		}
		.day-tab {
			min-width: auto;
			padding: 0.75rem 1rem;
		}
	}
</style>
