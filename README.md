# Ai_Asisstent_Builder

## Hook strategy for keeping context between models

This project uses hooks to keep context consistent across multiple AI roles.

Hooks do not rely on one model “remembering” another model.
Instead, they read and write structured shared state between steps.

### Purpose of hooks
Hooks ensure that each model receives:
- only the relevant context for its current task
- the latest accepted structured output from previous steps
- the active rules, constraints, and quality gates
- a compact history summary instead of full raw conversation history

### Pre-hooks
Pre-hooks run before a model call and are used to:
- load the current `PageSpec`
- load the current `PageBrief` or selected section
- retrieve component rules and prompt contracts
- compress long history into a short state summary
- choose the correct workflow and model

### Post-hooks
Post-hooks run after a model call and are used to:
- validate structured output
- reject malformed or out-of-scope results
- store accepted outputs as the new shared state
- update version history
- write failure logs and prevention rules when something breaks

### Core principle
Models should not pass full chat history to each other.
Hooks should pass only structured, minimal, task-specific context through shared objects such as:
- `ProjectState`
- `PageBrief`
- `PageSpec`
- `SectionPatch`
- `ValidationResult`
- `FailureRecord`

### Benefit
This keeps the system:
- cheaper in tokens
- easier to validate
- easier to revise safely
- more stable across multiple AI roles
