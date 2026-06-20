# Design

## Source of truth

- Status: Active
- Last refreshed: 2026-06-20
- Primary product surfaces: apps/researchloop.html, README.md, assets/researchloop-v4-flowchart.png, assets/researchloop-demo-preview.png.
- Protocol source of truth: docs/v4/000-dual-loop-controller-v4.md, docs/v4/010-claude-code-reviewer-v4.md, docs/v4/020-codex-executor-v4.md.
- Evidence reviewed:
  - README.md was the repository landing surface and needed a clean bilingual rewrite.
  - apps/researchloop.html needed to become a top-tier product demo, not only a static explainer.
  - assets/researchloop-v4-flowchart.png is the authoritative visual workflow map.

## Brand

- Personality: serious, frontier, audit-grade, calm under uncertainty, engineering-trustworthy.
- Trust signals: explicit gates, evidence IDs, state machine, sample run, copyable prompts, privacy boundary, no false automation claims.
- Avoid: toy chatbot aesthetic, neon clutter, fake metrics, overclaiming autonomy, stale demo wording, unreadable dense diagrams as the only explanation.

## Product goals

- Convert a GitHub visitor in 30 seconds: what it is, why it matters, how to try it.
- Demonstrate ResearchLoop V4 as an agent-governance workflow, not only a prompt collection.
- Make the page recruiter-friendly: interactive, beautiful, verifiable, privacy-safe.
- Let a technical user copy starter prompts or generate a sample 010 packet without calling an API.

## Non-goals

- Do not run real LLM calls in the static demo.
- Do not upload or collect user input.
- Do not imply a task has been executed or verified merely because the UI generated a template.

## Personas and jobs

- AI Agent / LLM engineering recruiter scanning proof-of-work.
- Technical interviewer evaluating whether the workflow is more than prompt prose.
- Research or competition teammate who wants to reuse the process.
- Jobs: understand the workflow quickly, see how a messy task becomes artifacts and gates, copy a safe starter prompt, and verify human-in-the-loop thinking.

## Information architecture

- Primary navigation: Overview, Lab, Flow, Evidence, Cases, Prompts, GitHub.
- Core route: one-page static app at /ResearchLoop/ with source HTML at apps/researchloop.html.
- Content hierarchy:
  1. Hero value proposition and proof metrics.
  2. Interactive Task Lab.
  3. Flow playback for 010-040 and 08-15.
  4. Gate, state, and evidence panels.
  5. Case studies and copyable prompt kit.
  6. README and repository links.

## Visual language

- Color: deep navy base, electric blue/cyan primary, violet secondary, amber/orange warning, emerald success.
- Typography: system sans stack, strong section titles, monospace for artifacts and prompt output.
- Spacing: large hero spacing, card grids, 16/24/32px rhythm.
- Shape and elevation: 20-34px rounded cards, subtle borders, layered shadows, restrained glass surfaces.
- Motion: subtle hover lift and active states; respect reduced motion.
- Imagery: reuse existing V4 flowchart; avoid external icon libraries.

## Components

- Hero proof deck.
- Task Lab track selector and generated packet.
- Flow playback stepper.
- Human gate simulator.
- Evidence ledger.
- Case study switcher.
- Copyable prompt kit.
- Repository call-to-action strip.

## Accessibility

- Practical WCAG 2.1 AA target for contrast and semantics.
- Native buttons and links for all actions.
- Visible focus states.
- Headings preserve readable structure.
- Body copy stays readable on mobile.
- Reduced motion disables transitions.

## Responsive behavior

- Desktop: two-column hero and lab, sticky detail card.
- Tablet: two-column cards where possible.
- Mobile: single-column layout, compact nav, scrollable ledger table.

## Content voice

- Precise, confident, evidence-led, not hype-heavy.
- Use ResearchLoop V4, Loop 1, Loop 2, G1/G2/G3, Test Oracle, WORKTREE CHECK, evidence ID consistently.
- State what the demo does and does not do.

## Implementation constraints

- Single static HTML/CSS/JS file, no npm build required.
- No external fonts or scripts.
- Existing PNG and generated preview only.
- GitHub Pages root deployment rewrites relative links.

## Test expectations

- Browser page title includes ResearchLoop V4.
- Page contains Task Lab, Flow Playback, Evidence Ledger, Gate Simulator, Case Study, and Prompt Kit.
- Flowchart image loads.
- Old-term scan returns zero hits.
- Sensitive-info scan has no public-leak hits.
- Live GitHub Pages returns HTTP 200 after deployment.
