# AI_ROLE_MATRIX

## Important note
I cannot verify the exact current model catalog available in your private environment from here.
So this file is written as a **role-to-capability selection matrix**.
Replace placeholders with the exact model names you have access to.

## Selection rule
Use the best fit **by capability**, not one model for all tasks.

## Role 1: Strategic Planner
### Best capability profile
- strongest reasoning
- high-context planning capability
- good architectural thinking
- good at tradeoff analysis

### Use for
- project scope
- architecture
- V1 promise
- orchestration design
- quality gate design
- implementation sequencing

### Model selection guidance
Choose the **highest-reasoning frontier model** available in your environment.

## Role 2: Critical Reviewer / Refactorer
### Best capability profile
- strong reasoning
- contradiction detection
- architecture criticism
- requirement simplification

### Use for
- plan review
- scope reduction
- logic consistency checks
- challenge hidden assumptions

### Model selection guidance
Choose the **same strongest reasoning model** or the strongest review-capable model available.

## Role 3: Implementer
### Best capability profile
- strong code generation
- precise instruction following
- good refactoring behavior
- consistent file edits

### Use for
- implementing atomic steps
- writing code from specs
- following markdown rules
- updating docs alongside code

### Model selection guidance
Choose the **best code-specialized model** available in your environment.
If unavailable, choose the best instruction-following model with strong coding performance.

## Role 4: Router / Formatter / Routine transform worker
### Best capability profile
- cheap
- fast
- structured output reliability
- good classification

### Use for
- request classification
- small JSON transforms
- light normalization
- copy trimming

### Model selection guidance
Choose a **smaller, lower-cost structured-output model**.

## Role 5: Failure Analyst
### Best capability profile
- strong reasoning
- root-cause analysis
- comparison of attempts
- clear explanation

### Use for
- stuck blockers
- architectural conflicts
- repeated implementation failures
- creating AI handoff packages

### Model selection guidance
Choose a **strong reasoning model** rather than the cheapest code model.

## Suggested decision table template
| Role | Capability needed | Exact model in your environment | Why chosen |
|---|---|---|---|
| Strategic Planner | highest reasoning | TO_FILL | TO_FILL |
| Critical Reviewer | highest reasoning | TO_FILL | TO_FILL |
| Implementer | best coding/instruction following | TO_FILL | TO_FILL |
| Router/Formatter | low-cost structured output | TO_FILL | TO_FILL |
| Failure Analyst | reasoning + diagnosis | TO_FILL | TO_FILL |

## Last refactor note
The “best AI” is the one chosen by role fit. Record final selected models here after checking your actual available catalog.
