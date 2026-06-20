# Design

## Source of truth
- Status: Active
- Last refreshed: 2026-06-20
- Primary product surfaces: `index.html`, `apps/researchloop.html`, `apps/index.html`, `README.md`, `assets/researchloop-v4-flowchart.png`, `assets/researchloop-demo-preview.png`.
- Protocol source of truth: `docs/v4/000-dual-loop-controller-v4.md`, `docs/v4/010-claude-code-reviewer-v4.md`, `docs/v4/020-codex-executor-v4.md`.
- Evidence reviewed:
  - The three `docs/v4` protocol files are byte-for-byte identical to the local updated prompt directory.
  - The previous Demo visually showed two loops but compressed Loop 1 into `010/030/035/040` and compressed Loop 2 into `PLAN/EXEC/RETRO/REVIEW`; it did not strictly expose `012/015/020`, `INSTRUCTION LOAD CHECK`, `WORKTREE CHECK`, `PLAN AUDIT`, or the `NNN`同号交付链.
  - User requirement: Chinese-first, GitHub portfolio quality, dynamic gradients, clickable state changes, and explicit per-step deliverables.

## Brand
- Personality: frontier, audit-grade, evidence-led, calm under uncertainty, suitable for AI Agent internship portfolio review.
- Trust signals: strict source mapping, named handoff files, role separation, evidence IDs, hard gates, no real API calls, no private data.
- Avoid: generic chatbot demo, single-color flat flowchart, vague “AI collaboration” claims, hidden deliverables, implying a static page performs real LLM execution.

## Product goals
- Goals:
  - Within 10 seconds, show that ResearchLoop is a **two-loop governance system**, not a prompt collection.
  - Make Loop 1 clearly read as “方案脑暴 / 路线校验层（做对的事）”.
  - Make Loop 2 clearly read as “协同交付 / 执行验证层（把事做对）”.
  - Every node must show current action, handoff artifact, evidence, next step, and why failure loops back.
- Non-goals:
  - No backend execution, no LLM API calls, no data upload.
  - No private local paths or personal information in public files.
  - No claim that `implemented` equals `verified`.
- Success signals:
  - Demo contains visible nodes for `010/012/015/020/030/035/040`.
  - Demo contains visible nodes for `CC-R/LOAD/PLAN/G2/WORKTREE/CODEX/RETRO/CC-V/G3`.
  - Clicking nodes updates details, evidence, prompt, and state chain.
  - README explains the workflow using GitHub-friendly preview, quick mechanism, and repo map.

## Personas and jobs
- Primary personas: AI Agent/LLM internship recruiter, technical interviewer, future teammate, GitHub visitor.
- User jobs: quickly understand the workflow, inspect role boundaries, verify deliverables, copy a starting prompt, see why loops reduce risk.
- Key contexts of use: GitHub Pages link in resume, GitHub README scan, interview screen share, mobile quick view.

## Information architecture
- Primary navigation: 为什么循环, 动态双循环, 010 输入包, 证据链, 提示词, 完整图, GitHub.
- Core routes/screens:
  - `/` and `/apps/` static pages.
  - `apps/researchloop.html` source page.
- Content hierarchy:
  1. Hero: strict V4 dual-loop value proposition.
  2. Why loops: direction risk vs execution drift.
  3. Dynamic control room: clickable protocol nodes.
  4. Linked evidence/prompt panels.
  5. 010 Packet Lab.
  6. Full V4 flowchart and GitHub CTA.

## Design principles
- Principle 1: The loop is the product; animation must explain feedback, not decorate.
- Principle 2: A node is incomplete unless it names a file artifact.
- Principle 3: Evidence beats assertions; use IDs and handoff files everywhere.
- Tradeoffs: Keep a no-build static HTML implementation for GitHub Pages reliability instead of adding a framework.

## Visual language
- Color: dark navy base with cyan for Loop 1 reasoning, violet for Claude/plan review, emerald for Codex/execution success, amber/red for risk/BLOCKER.
- Typography: system sans for Chinese readability; monospace for file names, evidence IDs, and prompt snippets.
- Spacing/layout rhythm: dense control-room cards, 12-18px card gaps, large hero with readable sections.
- Shape/radius/elevation: glass panels, rounded cards, glowing active nodes, gradient hero.
- Motion: animated gradient background, active-node pulse, auto-play step transitions; respect `prefers-reduced-motion`.
- Imagery/iconography: CSS loop mark plus existing full V4 flowchart image.

## Components
- Existing components to reuse: V4 flowchart image, README preview image, static HTML control room.
- New/changed components:
  - “为什么必须循环” section.
  - Strict 010-040 node list.
  - Strict Loop2 handoff chain nodes.
  - Node detail panel with “当前交接物” and “交接/回环理由”.
  - Expanded 010 Packet Lab output.
- Variants and states: draft, risk, blocker, pass, hard gate, implemented, G3 candidate, verified.
- Token/component ownership: inline CSS variables in `apps/researchloop.html`; root/app entry files are generated copies.

## Accessibility
- Target standard: practical WCAG 2.1 AA.
- Keyboard/focus behavior: nodes and controls are native buttons/links.
- Contrast/readability: dark surfaces with high-contrast text and non-color text labels for states.
- Screen-reader semantics: headings, `aria-live` cockpit, descriptive alt text for the flowchart.
- Reduced motion and sensory considerations: media query disables animation and transitions.

## Responsive behavior
- Supported breakpoints/devices: desktop, tablet, mobile browser.
- Layout adaptations: desktop uses control room + cockpit; tablet/mobile collapse to single column.
- Touch/hover differences: all information appears in labels and panels, not hover-only.

## Interaction states
- Loading: static page; default active node is `010`.
- Empty: Packet Lab has a sample task.
- Error: clipboard failure changes copy button to manual-copy hint.
- Success: copy button briefly changes to `已复制`.
- Disabled: no hidden disabled controls.
- Offline/slow network: all text works offline after assets load.

## Content voice
- Tone: Chinese-first, precise, evidence-led, interview-ready.
- Terminology: ResearchLoop V4, Loop 1 方案脑暴 / 路线校验层, Loop 2 协同交付 / 执行验证层, 010-040, G1/G2/G3, Test Oracle, PLAN AUDIT, WORKTREE CHECK, CC-R/CX-R/CC-V.
- Microcopy rules: every workflow claim should name an artifact or evidence ID; avoid vague “智能协作” phrasing.

## Implementation constraints
- Framework/styling system: single static HTML/CSS/JS file, no npm build required.
- Design-token constraints: CSS variables at top of HTML.
- Performance constraints: no external fonts/scripts; only local image assets.
- Compatibility constraints: GitHub Pages, modern Chrome/Edge/Safari/Firefox.
- Test/screenshot expectations: protocol keyword scan, mojibake scan, sensitive-info scan, local browser smoke test, screenshot refresh.

## Open questions
- [ ] If future GitHub Pages source folder changes, confirm whether `/`, `/apps/`, or GitHub Actions artifact is authoritative.
- [ ] Consider adding a short animated GIF preview if the README needs higher click-through later.
