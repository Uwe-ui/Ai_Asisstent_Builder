# QUALITY_GATES

# Master Rule
No implementation without written scope.
No acceptance without quality gates.
No failure without logging.
No repeated mistake without a prevention rule.

## Gate A: Planning quality gate
Implementation may not start until the following exist:
- written project scope
- V1 promise
- non-goals
- architecture summary
- implementation plan
- prompt contracts
- failure logging process

## Gate B: Input / request gate
Before any workflow runs:
- request type must be identified
- unsupported requests must be rejected
- revision scope must be clear
- required context must be retrievable

## Gate C: Schema gate
A generated artifact fails immediately if:
- top-level fields are missing
- section objects lack required fields
- unknown shapes appear
- malformed structured output cannot be repaired safely

## Gate D: Component gate
A generated artifact fails if:
- it uses non-approved components
- section order is irrational for the page type
- required core sections are missing without documented reason

## Gate E: Renderability gate
A generated artifact fails if:
- the deterministic renderer cannot map every section to a component
- required props are missing
- build/runtime rendering would break

## Gate F: Revision safety gate
For a revision request:
- unrelated sections must remain unchanged
- layout must not change during copy-only edits
- forbidden fields must not be modified

## Gate G: UX/content gate
A generated artifact fails or warns if:
- headline is empty or unclear
- CTA is missing
- page has no trust/proof signal
- text length exceeds defined limits
- content contradicts the prompt

## Gate H: Learning gate
After any meaningful failure:
- a failure log entry is required
- a prevention rule must be proposed
- a test, contract, or doc rule should be added if the issue is repeatable

## Gate I: Stop gate
Stop and wait for approval if:
- the same blocker fails 3 times
- a core architecture conflict appears
- quality cannot be established safely
