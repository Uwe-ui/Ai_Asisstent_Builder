# IMPLEMENTATION_PLAN

## Execution rule
No implementation without written scope.
Implement one atomic step at a time.
After each step, record what changed, how it is tested, and what the user can now do.

## Phase 0: Governance foundation
### Step 0.1
Create governance docs.
**Files:** all base markdown docs
**Output:** documented project rules
**Validation:** all required docs exist

### Step 0.2
Define `PageSpec` schema and component catalog.
**Files:** `PROMPT_CONTRACTS.md`, `COMPONENT_CATALOG.md`
**Output:** stable structure contract
**Validation:** required fields and approved components documented

## Phase 1: Deterministic foundation
### Step 1.1
Build React section library for approved components.
**Files:** component files only
**Output:** deterministic renderable components
**Validation:** each component renders with valid props

### Step 1.2
Build `PageRenderer` that consumes `PageSpec`.
**Files:** renderer files
**Output:** preview from JSON works
**Validation:** sample valid `PageSpec` renders end-to-end

### Step 1.3
Add schema validation for `PageSpec`.
**Files:** schema validation files
**Output:** invalid specs are rejected before render
**Validation:** known invalid examples fail

## Phase 2: First AI workflow
### Step 2.1
Create `create_page` workflow.
**Files:** router/planner/spec-generator integration
**Output:** one prompt -> one valid portfolio `PageSpec`
**Validation:** passes schema, component, and renderability gates

### Step 2.2
Store versioned output.
**Files:** persistence layer
**Output:** prompt, spec, validation result stored
**Validation:** previous versions retrievable

## Phase 3: Revision workflow
### Step 3.1
Implement `revise_section` workflow.
**Output:** prompt changes one section only
**Validation:** unrelated sections are unchanged

### Step 3.2
Implement `rewrite_copy` workflow.
**Output:** text updates without layout drift
**Validation:** structure identical before/after

## Phase 4: Orchestration hardening
### Step 4.1
Add pre-hooks and post-hooks.
**Output:** controlled lifecycle
**Validation:** hook execution is logged

### Step 4.2
Add stop conditions and failure handoff creation.
**Output:** blocked problems are documented clearly
**Validation:** after 3 failures system stops and writes handoff prompt

## Phase 5: Learning loop
### Step 5.1
Add failure logging + prevention rule workflow.
**Output:** failures create learning artifacts
**Validation:** repeatable issues always produce a prevention rule

### Step 5.2
Add eval cases and regression cases.
**Output:** common failures are testable
**Validation:** known bad cases remain blocked
