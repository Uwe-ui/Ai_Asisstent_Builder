# ARCHITECTURE

## High-level architecture

```text
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

## Core architectural decision
`PageSpec` JSON is the source of truth in V1.

```text
Prompt -> PageBrief -> PageSpec JSON -> Renderer -> React UI
```

## Main layers

### 1) UI Layer
Responsible for:
- taking prompts
- showing preview
- showing validation status
- showing revision history
- showing failure explanations

Suggested stack:
- Next.js
- React
- TypeScript
- Tailwind CSS

### 2) Orchestration Layer
Responsible for:
- request classification
- workflow routing
- hook execution
- retrieving current state
- calling the right AI role
- handling retries and stop conditions

### 3) AI Layer
Responsible for:
- creating a structured page brief
- generating a `PageSpec`
- changing only approved parts on revision
- producing structured outputs only

### 4) Validation Layer
Responsible for:
- schema validation
- allowed component validation
- required field validation
- revision scope validation
- renderability checks

### 5) Rendering Layer
Responsible for:
- deterministic conversion from `PageSpec` to React components
- consistent design enforcement
- keeping code stable while content/structure changes via `PageSpec`

### 6) Persistence Layer
Responsible for:
- storing projects
- storing page versions
- storing prompts
- storing failed attempts
- storing decisions and learnings

## Suggested repo structure

```text
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

## Canonical entities
- Project
- Page
- PageSpec
- SectionSpec
- Version
- RevisionPrompt
- ValidationResult
- FailureRecord
- LearningRecord

## Why this architecture
- It prevents AI from becoming the renderer.
- It keeps UI deterministic.
- It creates clean validation boundaries.
- It makes selective revisions possible.
- It supports learning logs and rollback.
