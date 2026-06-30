# AI-Assisted Website Builder Governance Pack

This pack contains the planning, governance, workflow, quality, learning, and AI role-selection files for your project.

## Core idea
Build an AI-assisted system for planning, creating, reviewing, and implementing website features through controlled workflows, strict quality gates, and documented learning from failures.

## Master operating rule
No implementation without written scope.
No acceptance without quality gates.
No failure without logging.
No repeated mistake without a prevention rule.

## V1 promise
Build one valid portfolio onepager from one prompt using only approved components and a strict `PageSpec` JSON schema.

## Source of truth
`PageSpec` JSON is the single source of truth in V1.
AI may create and revise `PageSpec`.
The renderer deterministically turns `PageSpec` into React components.
Generated React code is **not** the source of truth in V1.
