# MISSING_SKILLS

## Purpose
Track knowledge gaps that affect design quality or implementation speed.

## Priority scale
- P1 = blocking
- P2 = important soon
- P3 = useful later

## Current skill gaps

### 1) Router design
- **Priority:** P1
- **Why it matters:** decides which workflow handles which request
- **Need to learn:** classification logic, workflow boundaries, confidence handling

### 2) Pre-hooks and post-hooks
- **Priority:** P1
- **Why it matters:** create control points around AI calls
- **Need to learn:** when to sanitize, retrieve, validate, retry, and log

### 3) Retrieval / context selection
- **Priority:** P1
- **Why it matters:** reduces token waste and improves accuracy
- **Need to learn:** section-level context retrieval, compact project state, prompt scoping

### 4) `PageSpec` schema design
- **Priority:** P1
- **Why it matters:** source of truth quality determines system stability
- **Need to learn:** required fields, versioning, section contracts

### 5) Schema validation (e.g., Zod)
- **Priority:** P1
- **Why it matters:** prevents bad AI output from entering the renderer

### 6) Deterministic rendering from JSON
- **Priority:** P1
- **Why it matters:** separates AI creativity from frontend reliability

### 7) Prompt contracts
- **Priority:** P2
- **Why it matters:** keeps AI outputs structured and testable

### 8) Version history / rollback
- **Priority:** P2
- **Why it matters:** safe revisions and debugging

### 9) Evaluation / regression thinking
- **Priority:** P2
- **Why it matters:** prevents repeated failures

### 10) Token optimization principles
- **Priority:** P2
- **Why it matters:** cost and stability

## Rule
When a skill gap causes a real blocker, add a linked entry in `FAILURE_LOG.md`.
