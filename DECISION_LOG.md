# ORCHESTRATION_RULES

## Plain-language definitions

### Router
A router decides what kind of request has arrived and which workflow should handle it.
It does not create the final page. It chooses the path.

### Hooks
Hooks are normal code functions that run before or after AI steps.
They are control points, not AI magic.

### Retrieval
Retrieval means loading only the information needed right now.
Examples:
- current `PageSpec`
- selected section only
- component rules
- style/token rules
- relevant decision history

## Workflow types (V1 + near-V1)
1. `create_page`
2. `revise_section`
3. `rewrite_copy`
4. `change_style_within_allowed_tokens`
5. `explain_validation_failure`

## Workflow A: create_page
```text
User prompt
-> classify intent
-> extract page goal / audience / tone
-> build PageBrief
-> choose allowed components
-> generate PageSpec JSON
-> validate schema
-> validate components
-> render preview
-> store version + decision logs
```

## Workflow B: revise_section
```text
Revision prompt
-> identify target section(s)
-> retrieve current PageSpec
-> limit scope of change
-> generate SectionPatch or partial PageSpec
-> validate revision boundaries
-> rerender
-> store diff + reason
```

## Workflow C: rewrite_copy
```text
Prompt
-> identify section(s)
-> preserve layout and allowed structure
-> regenerate text fields only
-> validate length/tone constraints
-> rerender
```

## Pre-hooks
- sanitize prompt
- classify request
- load current project state
- load component catalog
- enforce allowed components
- estimate context size
- choose AI role/model tier
- stop unsupported requests early

## Post-hooks
- parse structured output
- validate against schema
- reject unknown fields
- trim overly long copy
- compare with previous version
- store logs
- create failure entry if needed

## Stop conditions
- After 3 failures on the same blocker, stop and wait for approval.
- If schema cannot be repaired safely, do not accept output.
- If the request exceeds allowed V1 scope, reject with explanation.

## Retrieval rules
- Never send the full project state if only one section changes.
- Never send full rendered code to the model if `PageSpec` is sufficient.
- Prefer section-level context over page-level context where possible.
- Summarize long histories into compact state notes.
