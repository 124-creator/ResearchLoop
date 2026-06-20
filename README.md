# ResearchLoop V4 · Multi-Agent Workflow Governance

[Live Demo](https://124-creator.github.io/ResearchLoop/) · [V4 Protocol](./docs/v4/000-dual-loop-controller-v4.md) · [Plan Template](./templates/v4-plan-template.md) · [MIT License](./LICENSE)

ResearchLoop V4 is a dual-loop workflow for AI-agent work that must be correct, reviewable, and reproducible. It turns an ambiguous request into gated artifacts: problem definition, risk map, evidence baseline, route comparison, independent review, executable plan, worktree check, tests, and final acceptance.

中文简介：ResearchLoop V4 是一套面向 AI Agent 工程与科研协作的工作流方法。它不是单一提示词，而是把需求确认、风险地图、证据链、独立审查、执行隔离与验收门组织成可复用的公开项目。

## Preview

![ResearchLoop V4 demo preview](./assets/researchloop-demo-preview.png)

## Live Demo

Open: https://124-creator.github.io/ResearchLoop/

The demo is a static, privacy-safe page. It runs fully in the browser and does not upload text or call external APIs.

## Why it matters

Most agent failures are not just model failures. They come from unclear goals, hidden risk, missing evidence, no reviewer, and no stop condition. ResearchLoop V4 makes these failure modes visible before execution.

## What makes it different

| Ordinary agent prompt | ResearchLoop V4 |
| --- | --- |
| Starts implementing while the problem is still moving. | Routes the task by uncertainty, risk, and file scope before touching files. |
| Keeps assumptions, code, and review in one chat thread. | Produces traceable artifacts from 010 to 040 and from WORKTREE CHECK to G3. |
| Has weak rollback and unclear evidence. | Requires a Test Oracle, evidence IDs, and a retrospective. |
| Hard to explain in an interview. | Provides an interactive demo, templates, and public docs. |

## Interactive Demo includes

- Task Lab: turn a messy request into a first 010 problem packet.
- Flow Playback: click each Loop 1 and Loop 2 step to see owner, gate, and artifact.
- Gate Simulator: see how draft, approved, implemented, and verified states depend on evidence.
- Evidence Ledger: sample trace IDs for review, implementation, tests, and acceptance.
- Case Study Replay: examples for modeling, research-agent pipelines, and portfolio delivery.
- Prompt Kit: copy starter prompts for problem definition, independent review, and execution.

## Quick Start

1. Open the live demo.
2. Inspect the protocol: ./docs/v4/000-dual-loop-controller-v4.md
3. Use the templates: ./templates/v4-plan-template.md and ./templates/v4-retrospective-block-template.md
4. Read the executor contract: ./AGENTS.md
5. Run the page locally by opening ./apps/researchloop.html in a browser.

## Protocol map

### Loop 1 · 方案层：做对的事

- 010 Problem Definition: goal, non-goals, privacy boundary, acceptance criteria.
- 012 Risk Map: uncertainty, external writes, rollback, data sensitivity.
- 015 Evidence Baseline: facts, prior failures, references, confidence grade.
- 020 Candidate Routes: compare R1/R2/R3 instead of jumping to implementation.
- 030 Independent Review: BLOCKER, RISK, or PASS.
- 035 Route Decision: lock route, deliverable manifest, rejected alternatives.
- 040 Test Oracle: define the smallest checks that prove completion.

### Loop 2 · 协同交付层：把事做对

- Repo exploration and instruction load check.
- Draft plan, plan audit, and G2 execution gate.
- WORKTREE CHECK before modifying files.
- Bounded implementation, tests, and evidence capture.
- Final review and G3 human acceptance.

State chain: draft → approved → implemented → verified.

## Repository map

~~~text
ResearchLoop/
├─ apps/                      Static interactive demo
├─ assets/                    Flowchart and preview image
├─ docs/v4/                   V4 protocol source of truth
├─ examples/                  Example workflow artifacts
├─ templates/                 Plan and retrospective templates
├─ AGENTS.md                  Executor contract
├─ DESIGN.md                  Design source of truth for the demo
└─ README.md                  Repository landing page
~~~

## Privacy Boundary

This public repository should not contain private datasets, credentials, personal contact information, local absolute paths, or active competition submission packages. The demo is designed as a portfolio-safe explanation of the workflow, not as a backend service.

## Status

- Current focus: V4 public demo and workflow documentation.
- Deployment target: GitHub Pages.
- Verification style: local browser check, old-term scan, sensitive-info scan, live page HTTP check, and screenshot preview.

## License

MIT License.
