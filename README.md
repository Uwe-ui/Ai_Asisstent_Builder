# AI Assistant Builder

> An AI-assisted system for planning, creating, reviewing, and implementing website features — governed by strict workflows, quality gates, and documented learning from failures.

---

## Overview

**AI Assistant Builder** is a controlled, AI-powered website builder that generates portfolio onepager sites from a single prompt. It uses a structured `PageSpec` JSON as the single source of truth and deterministically renders React components from that spec.

---

## Core Principle

> **No implementation without written scope.**  
> **No acceptance without quality gates.**  
> **No failure without logging.**  
> **No repeated mistake without a prevention rule.**

---

## V1 Promise

Build one valid **portfolio onepager** from one prompt using only approved components and a strict `PageSpec` JSON schema.

---

## Architecture

```
User Prompt
-> Router
-> Workflow Selector
-> Pre-hooks
-> Retrieval
-> AI Step(s)
-> Post-hooks
-> Quality Gate / Validation
-> Renderer
-> Version Store + Logs + Learnings
```

### Source of Truth Flow

```
Prompt -> PageBrief -> PageSpec JSON -> Renderer -> React UI
```

The **`PageSpec` JSON** is the source of truth in V1.  
AI creates and revises `PageSpec`. The renderer deterministically converts it to React components. Generated React code is **not** the source of truth.

---

## Tech Stack

| Layer | Technology |
|---|---|
| UI | Next.js, React, TypeScript, Tailwind CSS |
| Orchestration | Node.js / TypeScript hooks |
| AI Layer | Role-based model selection |
| Validation | Zod schema validation |
| Persistence | Versioned JSON store |

---

## Approved Components (V1)

| Component | Purpose |
|---|---|
| `Hero` | Headline, subheadline, primary CTA |
| `About` | Background, focus, style of work |
| `Projects` | Portfolio items with impact and tags |
| `SkillsServices` | Skills or services list |
| `TestimonialsProof` | Quotes, metrics, client names |
| `ContactCTA` | Contact link, social links, availability |

**Recommended section order:**
1. Hero
2. About
3. Projects
4. SkillsServices
5. TestimonialsProof
6. ContactCTA

---

## Workflows (V1)

| Workflow | Description |
|---|---|
| `create_page` | One prompt → one valid `PageSpec` |
| `revise_section` | Change one section without touching others |
| `rewrite_copy` | Update text without changing layout |
| `change_style` | Style changes within approved tokens |
| `explain_failure` | Describe and log a validation failure |

---

## Quality Gates

| Gate | Rule |
|---|---|
| A — Planning | No implementation without written scope, architecture, and prompt contracts |
| B — Input | Request type must be identified before any workflow runs |
| C — Schema | Missing or malformed structured output fails immediately |
| D — Component | Only approved components are allowed |
| E — Renderability | Every section must map to a renderable component |
| F — Revision safety | Unrelated sections must not change during a revision |
| G — UX/Content | Headlines, CTAs, and trust signals must be present |
| H — Learning | Every meaningful failure produces a log entry and a prevention rule |
| I — Stop | After 3 failures on the same blocker, stop and wait for approval |

---

## Project Structure

```
ai-site-builder/
├── app/
│   ├── editor/
│   ├── projects/
│   ├── preview/
│   └── api/
├── components/
│   ├── sections/
│   ├── renderer/
│   └── ui/
├── lib/
│   ├── ai/
│   ├── orchestration/
│   ├── schemas/
│   ├── data/
│   └── utils/
├── docs/
├── prompts/
├── evals/
└── ai_handoffs/
```

---

## Implementation Phases

| Phase | Description | Status |
|---|---|---|
| 0 | Governance foundation — docs, schema, contracts | 📋 Planned |
| 1 | Deterministic foundation — components, renderer, schema validation | 📋 Planned |
| 2 | First AI workflow — `create_page`, version storage | 📋 Planned |
| 3 | Revision workflows — `revise_section`, `rewrite_copy` | 📋 Planned |
| 4 | Orchestration hardening — hooks, stop conditions | 📋 Planned |
| 5 | Learning loop — failure logging, eval cases, regression cases | 📋 Planned |

---

## AI Role Strategy

This project uses **role-based model selection** — the best AI is chosen per task, not one model for everything:

| Role | Capability | Used For |
|---|---|---|
| Strategic Planner | Strongest reasoning | Scope, architecture, quality gates |
| Critical Reviewer | Contradiction detection | Plan review, scope reduction |
| Implementer | Best code generation | Atomic step implementation |
| Router / Formatter | Fast, structured output | Classification, transforms |
| Failure Analyst | Root-cause reasoning | Stuck blockers, handoff packages |

---

## Hook Strategy

Hooks keep context consistent across AI roles **without relying on one model remembering another**.

- **Pre-hooks** load current `PageSpec`, component rules, and compressed history before each AI call.
- **Post-hooks** validate output, reject malformed results, store accepted outputs, and write failure logs.

---

## Governance Documents

| File | Contents |
|---|---|
| `ARCHITECTURE.md` | System architecture and layers |
| `COMPONENT_CATALOG.md` | Approved components and required props |
| `PROMPT_CONTRACTS.md` | Structured output contracts for every AI role |
| `QUALITY_GATES.md` | All quality gates A–I |
| `ORCHESTRATION_RULES.md` | Workflows, hooks, retrieval rules, stop conditions |
| `IMPLEMENTATION_PLAN.md` | Phased implementation plan |
| `DECISION_LOG.md` | Key architectural decisions and rationale |
| `FAILURE_LOG.md` | Failure records and prevention rules |
| `LEARNING_LOG.md` | Improvements and lessons learned |

---

## License

To be added.
